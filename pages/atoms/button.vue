<template>
  <app-page :narrow="true">
    <h2 class="page-title">Buttons</h2>
    <div class="page-description mb-30">
      <p>Saratoga buttons are the most common call-to-action elements treated as atoms. The button classes can be used on diferent elements which expect user click.</p>
    </div>

    <el-row :gutter="20">
      <el-col :sm="24" :md="12">
        <h4>Demo</h4>
        <div class="page-content-demo stg-design mb-30">
          <div class="mb-10">
            <button class="button impact">Impact button</button>
          </div>
          <div class="mb-10">
            <button class="button impact disabled">Impact button disabled</button>
          </div>
          <div class="mb-10">
            <button class="button ghost">Ghost button</button>
          </div>
          <div class="mb-10">
            <button class="button promo">Promo button</button>
          </div>
          <div class="mb-10">
            <button class="button">Text button</button>
          </div>
          <div class="mb-10">
            <button class="button promo full-width">Full width button</button>
          </div>
          <div class="mb-10">
            <button class="button promo full-width-mobile">Full width on mobile</button>
          </div>

          <el-divider class="mt-40" content-position="left">Social buttons</el-divider>

          <div class="mb-10">
            <button class="button social facebook"><span>Sign in with facebook</span></button>
          </div>
          <div class="mb-10">
            <button class="button social google"><span>Sign in with google</span></button>
          </div>
          <div class="mb-10">
            <button class="button social apple"><span>Sign in with apple</span></button>
          </div>

          <el-divider class="mt-40" content-position="left">Buttons with spinners</el-divider>

          <div class="mb-10">
            <button class="button impact" :class="{'show-spinner': showSpinner}" @click="showSpinner = !showSpinner">
              <span>Click me to spin it</span>
              <span class="spinner white">
                <span class="spinner-dot"></span>
                <span class="spinner-dot"></span>
                <span class="spinner-dot"></span>
              </span>
            </button>

            <button class="button ghost" :class="{'show-spinner': showSpinnerGhost}" @click="showSpinnerGhost = !showSpinnerGhost">
              <span>Click me to spin the gost</span>
              <span class="spinner">
                <span class="spinner-dot"></span>
                <span class="spinner-dot"></span>
                <span class="spinner-dot"></span>
              </span>
            </button>
          </div>
        </div>
      </el-col>
      <el-col :sm="24" :md="12">
        <div class="page-content-code mb-30">
          <el-card>
            <el-tabs>
              <el-tab-pane label="HTML">
                <prism language="html" :lineNumbers="true" :readonly="true" :code="html"></prism>
              </el-tab-pane>
              <el-tab-pane label="CSS">
                <prism language="css" :lineNumbers="true" :readonly="true" :code="css"></prism>
              </el-tab-pane>
              <el-tab-pane label="Vue component">
                <prism language="html" :lineNumbers="true" :readonly="true" :code="component"></prism>
                <div class="docs">
                  <h4>Props:</h4>
                  <prop name="type" type="String">Values: impact, ghost, promo</prop>
                  <prop name="url" type="String">Value: url for the button</prop>
                  <prop name="block" type="Boolean">Values: true/false</prop>
                  <prop name="elementId" type="String">Value: ID</prop>
                </div>
              </el-tab-pane>
            </el-tabs>
          </el-card>
        </div>
      </el-col>
    </el-row>
  </app-page>
</template>

<script>
import AppPage from '@/components/AppPage'

import html from '@/content/atoms/buttons/html-markup.html'
import component from '@/content/atoms/buttons/component.html'
import css from '!!raw-loader!@/assets/scss/stg-design/atoms/_buttons.scss'

export default {
  layout: 'page-layout',
  head() {
    return {
      title: 'Button | Atoms'
    };
  },
  data() {
    return {
      html,
      css,
      component,
      showSpinner: false,
      showSpinnerGhost: false
    }
  }
};
</script>