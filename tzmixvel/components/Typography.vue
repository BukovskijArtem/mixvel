<template>
    <div>
      <div class="style-changes">
        <label>
          Settings
        </label>
        <select v-model="setTag">
          <option v-for="item in optionsTag" :key="item.id">{{ item.value }}</option>
        </select>
        <select v-model="setStyle">
          <option v-for="item in optionsStyle" :key="item.id">{{ item.value }}</option>
        </select>
        <input v-model="newStyle"/>
        <button @click="saveSet">Применить</button>
      </div>
      <h1>Test h1</h1>
      <a href="#">Test Link</a>
      <br/>
      <span>Test span</span>
      <p>Test p</p>

    </div>
</template>
<script>
export default {
    name: 'Typography',
    data() {
      return {
        newStyle: '',
        setTag: 'h1',
        optionsTag: [
          { value: 'h1', id: 1},
          { value: 'Link', id: 2},
          { value: 'span', id: 3},
          { value: 'p', id: 4}
        ],
        setStyle: 'Color',
        optionsStyle: [
          { value: 'Color', id: 1},
          { value: 'Line-height', id: 2},
          { value: 'Font-size', id: 3},
          { value: 'Font-style', id: 4},
          { value: 'Font-weight', id: 5},
        ],
        h1Color: '',
        h1LineHeight: '',
        h1FontSize: '2em',
        h1FontStyle: 'normal',
        h1FontWeight: 'bold',
        LinkColor: '-webkit-link',
        LinkLineHeight: '',
        LinkFontSize: '',
        LinkFontStyle: 'normal',
        LinkFontWeight: '',
        spanColor: '',
        spanLineHeight: '',
        spanFontSize: '',
        spanFontStyle: 'normal',
        spanFontWeight: '',
        pColor: '',
        pLineHeight: '',
        pFontSize: '',
        pFontStyle: 'normal',
        pFontWeight: ''
      }
    },
    methods: {
        saveSet () {
            switch (this.setTag) {
                case 'h1':
                  if (this.setStyle === 'Color') this.h1Color = this.newStyle
                  if (this.setStyle === 'Line-height') this.h1LineHeight = this.newStyle
                  if (this.setStyle === 'Font-size') this.h1FontSize = this.newStyle
                  if (this.setStyle === 'Font-style') this.h1FontStyle = this.newStyle
                  if (this.setStyle === 'Font-weight') this.h1FontWeight = this.newStyle
                break;
                case 'Link':
                  if (this.setStyle === 'Color') this.LinkColor = this.newStyle
                  if (this.setStyle === 'Line-height') this.LinkLineHeight = this.newStyle
                  if (this.setStyle === 'Font-size') this.LinkFontSize = this.newStyle
                  if (this.setStyle === 'Font-style') this.LinkFontStyle = this.newStyle
                  if (this.setStyle === 'Font-weight') this.LinkFontWeight = this.newStyle
                break;
                case 'span':
                  if (this.setStyle === 'Color') this.spanColor = this.newStyle
                  if (this.setStyle === 'Line-height') this.spanLineHeight = this.newStyle
                  if (this.setStyle === 'Font-size') this.spanFontSize = this.newStyle
                  if (this.setStyle === 'Font-style') this.spanFontStyle = this.newStyle
                  if (this.setStyle === 'Font-weight') this.spanFontWeight = this.newStyle
                break;
                case 'p':
                  if (this.setStyle === 'Color') this.pColor = this.newStyle
                  if (this.setStyle === 'Line-height') this.pLineHeight = this.newStyle
                  if (this.setStyle === 'Font-size') this.pFontSize = this.newStyle
                  if (this.setStyle === 'Font-style') this.pFontStyle = this.newStyle
                  if (this.setStyle === 'Font-weight') this.pFontWeight = this.newStyle
                break;
            }
        }
    }
}
</script>

<style>
.style-changes {
    padding-top: 20px;
}
h1 {
    color: v-bind(h1Color);
    line-height: v-bind(h1LineHeight);
    font-size: v-bind(h1FontSize);
    font-style: v-bind(h1FontStyle);
    font-weight: v-bind(h1FontWeight);
}
a {
    color: v-bind(LinkColor);
    line-height: v-bind(LinkLineHeight);
    font-size: v-bind(LinkFontSize);
    font-style: v-bind(LinkFontStyle);
    font-weight: v-bind(LinkFontWeight);
}
span {
    color: v-bind(spanColor);
    line-height: v-bind(spanLineHeight);
    font-size: v-bind(spanFontSize);
    font-style: v-bind(spanFontStyle);
    font-weight: v-bind(spanFontWeight);
}
p {
    color: v-bind(pColor);
    line-height: v-bind(pLineHeight);
    font-size: v-bind(pFontSize);
    font-style: v-bind(pFontStyle);
    font-weight: v-bind(pFontWeight);
}
</style>
