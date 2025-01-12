<script setup>

</script>

<template>
  <!-- content -->
  <div class="container">
    <!-- page header -->
    <div class="row header">
      <div class="col-12 col-md-8 offset-md-4">
        <div class="d-block image-holder cssanimation blurIn">
          <img class="img-fluid mb-2" src="~assets/img/portret-niels.jpg" />
        </div>
        <h1 class="mb-0">{{ $t('personalia.name') }}</h1>
        <span class="font-weight-bold lead">
            {{ $t('personalia.role') }}
          </span>
      </div>
    </div>

    <scroll-container @change="updateState">
      <div class="row mb-3">
        <!-- left sidebar (stack and tools) hide on mobile -->
        <div class="d-none d-lg-block col-lg-3 offset-lg-1 sidebar-start">
          <scroll-item id="stack-lg" class="cssanimation moveFromLeft">
            <div :class="state.index">
              <h3>{{ $t('headings.stack') }}</h3>
              <ul class="list-unstyled mb-5">
                <li v-for="(item, index) in $t('stack')" :key="index">
                  <span>{{ item.key }}</span>
                  <div class="float-right text-right mr-4">
                      <span
                          v-for="(bullet, i) in item.value"
                          :key="i"
                          class="ml-1"
                      >
                        &#8226;
                      </span>
                  </div>
                </li>
              </ul>
            </div>
          </scroll-item>
          <scroll-item id="tools-lg" class="cssanimation moveFromLeft">
            <div :class="state.index">
              <h3>{{ $t('headings.tools') }}</h3>
              <ul class="list-unstyled mb-5">
                <li v-for="(item, index) in $t('tools')" :key="index">
                  <span>{{ item.key }}</span>
                  <div class="float-right text-right mr-4">
                      <span
                          v-for="(bullet, i) in item.value"
                          :key="i"
                          class="ml-1"
                      >
                        &#8226;
                      </span>
                  </div>
                </li>
              </ul>
            </div>
          </scroll-item>
          <scroll-item id="interests-lg" class="cssanimation moveFromLeft">
            <div :class="state.index">
              <h3>{{ $t('headings.interests') }}</h3>
              <ul class="list-unstyled mb-5">
                <li
                    v-for="(item, index) in $t('interests')"
                    :key="index"
                    v-html="item"
                    class="mb-2"
                />
              </ul>
            </div>
          </scroll-item>
        </div>
        <div class="col-12 col-lg-7">
          <!-- profile header -->
          <h2 class="d-flex align-items-center">
              <span class="icon">
                <font-awesome-icon icon="user" />
              </span>
            {{ $t('headings.profile') }}
          </h2>
          <!-- about me -->
          <div class="content border-left mb-5">
            <p
                v-for="(paragraph, index) in $t('profile')"
                :key="index"
                v-html="paragraph"
            />
          </div>
          <!-- stack and tools mobile only  -->
          <div class="d-lg-none content border-left mb-5">
            <scroll-item id="stack">
              <div :class="state.index">
                <h3>{{ $t('headings.stack') }}</h3>
                <ul class="list-unstyled mb-5">
                  <li v-for="(item, index) in $t('stack')" :key="index">
                    <span>{{ item.key }}</span>
                    <div class="float-right text-right mr-4">
                        <span
                            v-for="(bullet, i) in item.value"
                            :key="i"
                            class="ml-1"
                        >
                          &#8226;
                        </span>
                    </div>
                  </li>
                </ul>
              </div>
            </scroll-item>
            <scroll-item id="tools">
              <div :class="state.index">
                <h3>{{ $t('headings.tools') }}</h3>
                <ul class="list-unstyled mb-5">
                  <li v-for="(item, index) in $t('tools')" :key="index">
                    <span>{{ item.key }}</span>
                    <div class="float-right text-right mr-4">
                        <span
                            v-for="(bullet, i) in item.value"
                            :key="i"
                            class="ml-1"
                        >
                          &#8226;
                        </span>
                    </div>
                  </li>
                </ul>
              </div>
            </scroll-item>
            <scroll-item id="interests">
              <div :class="state.index">
                <h3>{{ $t('headings.interests') }}</h3>
                <ul class="list-unstyled mb-5">
                  <li
                      v-for="(item, index) in $t('interests')"
                      :key="index"
                      v-html="item"
                      class="mb-2"
                  />
                </ul>
              </div>
            </scroll-item>
          </div>
          <!-- jobs experience header -->
          <h2 class="d-flex align-items-center">
              <span class="icon">
                <font-awesome-icon icon="folder" />
              </span>
            {{ $t('headings.experience') }}
          </h2>
          <!-- jobs experience -->
          <scroll-item
              v-for="(onejob, index) in $t('jobs')"
              :id="index"
              :key="index"
          >
            <job
                :periode="onejob.periode"
                :job="onejob.job"
                :company="onejob.company"
                :experience="onejob.experience"
                :class="state.index"
            />
          </scroll-item>
        </div>
      </div>
    </scroll-container>
  </div>
  <!-- back to top -->
  <div v-show="showUpButton" class="fixed-bottom">
    <button
        @click="scrollTo"
        type="button"
        class="btn btn-lg btn-outline-secondary float-right m-5"
    >
      <font-awesome-icon icon="angle-up" />
    </button>
  </div>
</template>

<style scoped>

</style>