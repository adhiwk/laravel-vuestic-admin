<template>
    <div class="row">
        <div
            v-for="(set, index) in sets"
            :key="index"
            class="va-card-wrapper flex lg6 xs12"
        >
            <va-card>
                <router-link
                    :to="{ path: `icons/${set.href}` }"
                    append
                    style="color: inherit"
                >
                    <div class="sets-list__set__content">
                        <div
                            class="sets-list__set__content__overlay pa-3 fill-height"
                        >
                            <va-button>
                                {{ set.name.toUpperCase() }}
                            </va-button>
                        </div>

                        <template
                            v-for="(filteredList, i) in set.filteredLists"
                        >
                            <div
                                v-if="filteredList.length !== 2"
                                :key="i"
                                class="row pa-3"
                            >
                                <div
                                    v-for="(icon, j) in filteredList"
                                    :key="j"
                                    class="sets-list__icon flex xs2"
                                >
                                    <div class="vuestic-icon">
                                        <va-icon :name="iconName(set, icon)" />
                                    </div>
                                </div>
                            </div>
                            <div
                                v-if="filteredList.length === 2"
                                :key="i"
                                class="row pa-3"
                                :class="
                                    i === 1
                                        ? 'sets-list__set__content--middle'
                                        : ''
                                "
                            >
                                <div class="sets-list__icon flex xs2">
                                    <div class="vuestic-icon">
                                        <va-icon
                                            :name="
                                                iconName(set, filteredList[0])
                                            "
                                        />
                                    </div>
                                </div>
                                <div class="flex xs8" />
                                <div class="sets-list__icon flex xs2">
                                    <div class="vuestic-icon">
                                        <va-icon
                                            :name="
                                                iconName(set, filteredList[1])
                                            "
                                        />
                                    </div>
                                </div>
                            </div>
                        </template>
                    </div>
                </router-link>
            </va-card>
        </div>
    </div>
</template>

<script setup lang="ts">
import { IconSet } from "./types";

defineProps<{
    sets: IconSet[];
}>();

const iconName = (set: IconSet, icon: string) => `${set.prefix}-${icon}`;
</script>

<style lang="scss">
.sets-list {
    &__icon {
        max-width: 1.5rem;
        display: flex;
        justify-content: center;
        align-items: center;

        .vuestic-icon {
            flex: 0 0 auto;
        }
    }

    &__set {
        position: relative;

        &__content {
            position: relative;

            &__overlay {
                display: flex;
                align-items: center;
                justify-content: center;
                padding: 0;
                margin: 0;
                width: 100%;
                position: absolute;
                z-index: 2;
            }
        }
    }
}
</style>
