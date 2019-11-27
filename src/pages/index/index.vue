<template>
  <div>
    <i-grid i-class="no-border">
    <i-grid-item i-class="no-border">
        <i-grid-icon>
            <image src="/static/images/burger.png" />
        </i-grid-icon>
        <i-grid-label>汉堡</i-grid-label>
    </i-grid-item>
    <i-grid-item i-class="no-border">
        <i-grid-icon>
            <image src="/static/images/chicken.png" />
        </i-grid-icon>
        <i-grid-label>炸鸡</i-grid-label>
    </i-grid-item>
    <i-grid-item i-class="no-border">
        <i-grid-icon>
            <image src="/static/images/drink.png" />
        </i-grid-icon>
        <i-grid-label>饮料</i-grid-label>
    </i-grid-item>
    <i-grid-item i-class="no-border">
        <i-grid-icon>
            <image src="/static/images/ice cream.png" />
        </i-grid-icon>
        <i-grid-label>甜品</i-grid-label>
    </i-grid-item>
  </i-grid>
  </div>
</template>

<script>

export default {
  data () {
    return {
    }
  },

  methods: {
  },

  created () {
  }
}
</script>

<style scoped>
div >>> .no-border{
  border-width:0pt;
}
div >>> .split{
  margin-bottom:10pt;
}
</style>
