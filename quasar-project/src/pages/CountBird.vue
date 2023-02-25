<template>
  <q-page>
    <div class="q-px-lg q-py-lg" style="font-family: 'Microsoft JhengHei'">
      <q-stepper v-model="step" ref="stepper" color="primary" animated>
        <q-step
          :name="1"
          title="上傳影片或照片"
          icon="photo_camera"
          :done="step > 1"
        >
          <q-file outlined v-model="file">
            <template v-slot:prepend>
              <q-icon name="attach_file" />
            </template>
          </q-file>
          <span>可上傳想進行辨識的影片或照片，越清晰效果會越好喔～</span>
        </q-step>

        <q-step
          :name="2"
          title="輸入當下時間、氣象條件"
          icon="today"
          :done="step > 2"
        >
          <span>
            請根據拍攝當時情況輸入相關資訊，另一預測功能將會根據此輸入資料而產生不同的結果
          </span>
        </q-step>

        <q-step
          :name="3"
          title="演算法辨識完成"
          icon="done_outline"
          :done="step > 3"
        >
          可觀察原圖與演算法標註後的差異，以及野鳥類別和數量
        </q-step>

        <q-step :name="4" title="進行標註" icon="highlight_alt">
          <div>可選擇要進行標註回饋的圖片</div>
          <div>＊相同的資料請勿重複回饋以免影響演算法準確性</div>
        </q-step>

        <template v-slot:navigation>
          <q-stepper-navigation>
            <q-btn
              @click="$refs.stepper.next()"
              color="primary"
              :label="step === 4 ? 'Finish' : 'Continue'"
            />
          </q-stepper-navigation>
        </template>
      </q-stepper>
    </div>
  </q-page>
</template>

<script>
export default {
  name: "CountBird",

  data() {
    return {
      step: 0,

      file: null,
    };
  },
};
</script>

<style></style>
