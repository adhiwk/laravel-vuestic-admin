<template>
    <div class="color-pickers vuestic-color-picker-page">
        <div class="row">
            <div class="flex md12 xs12">
                <va-card>
                    <va-card-title>{{ t("menu.colorPickers") }}</va-card-title>
                    <va-card-content class="row">
                        <div class="flex xs4 md2">
                            <div class="vuestic-color-picker-page__top-square">
                                <span
                                    class="title no-wrap"
                                    :style="{ color: colors.primary }"
                                >
                                    {{ t("colorPickers.simple") }}
                                </span>
                                <va-color-picker
                                    v-model="topSimpleSquareColor"
                                    :palette="palette"
                                />
                            </div>
                        </div>
                        <div class="flex xs4 md2">
                            <div class="vuestic-color-picker-page__top-square">
                                <span
                                    class="title no-wrap"
                                    :style="{ color: colors.primary }"
                                >
                                    {{ t("colorPickers.slider") }}
                                </span>
                                <va-color-picker
                                    v-model="topSliderSquareColor"
                                    mode="slider"
                                />
                            </div>
                        </div>
                        <div class="flex xs4 md2">
                            <div class="vuestic-color-picker-page__top-square">
                                <span
                                    class="title no-wrap"
                                    :style="{ color: colors.primary }"
                                >
                                    {{ t("colorPickers.advanced") }}
                                </span>
                                <va-color-input
                                    v-model="topAdvancedSquareColor"
                                    mode="advanced"
                                />
                            </div>
                        </div>
                    </va-card-content>
                </va-card>
            </div>
        </div>
        <div class="row">
            <div class="flex md12 xs12">
                <va-card>
                    <va-card-title>Simple Inline</va-card-title>
                    <va-card-content class="row">
                        <div class="flex md1">
                            <va-color-square :value="simpleColor" />
                        </div>
                        <div class="flex md2">
                            <va-color-palette
                                v-model="simpleColor"
                                :palette="palette"
                            />
                        </div>
                    </va-card-content>
                </va-card>
            </div>
        </div>
        <div class="row">
            <div class="flex md12 xs12">
                <va-card>
                    <va-card-title>Slider</va-card-title>
                    <va-card-content class="row">
                        <div class="flex xs12 md1">
                            <va-color-square :value="sliderColor" />
                        </div>
                        <div class="flex md6 xs12">
                            <va-color-slider v-model="sliderColor" />
                        </div>
                    </va-card-content>
                </va-card>
            </div>
        </div>
        <div class="row">
            <div class="flex md12 xs12">
                <va-card>
                    <va-card-title>Advanced</va-card-title>
                    <va-card-content class="row">
                        <div class="flex md1">
                            <va-color-square :value="advancedColor" />
                        </div>
                        <div class="flex md7">
                            <va-color-picker v-model="advancedColor" />
                        </div>
                    </va-card-content>
                </va-card>
            </div>
        </div>
    </div>
</template>

<script setup>
import { useColors } from "vuestic-ui";

const topSimpleSquareColor = "#f81953";
const topSliderSquareColor = "#34495e";
const topAdvancedSquareColor = "#ffd50a";
const sliderColor = "#2e5e2a";
const advancedColor = "#ffd50a";
const simpleColor = "#f81953";
const palette = [];
const { colors } = useColors();
</script>
