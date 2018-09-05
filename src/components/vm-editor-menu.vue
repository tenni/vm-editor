<template>
  <div class="vm-editor-menu">
    
    <VmEditorButton>
      <VmEditorDropdown>
        <ul class="vm-editor-ul">
          <li @click="execCommand('fontSize', 7)">
            <button style="font-size: 24px">7</button>
          </li>
          <li @click="execCommand('fontSize', 6)">
            <button style="font-size: 22px">6</button>
          </li>
          <li @click="execCommand('fontSize', 5)">
            <button style="font-size: 20px">5</button>
          </li>
          <li @click="execCommand('fontSize', 4)">
            <button style="font-size: 18px">4</button>
          </li>
          <li @click="execCommand('fontSize', 3)">
            <button style="font-size: 16px">3</button>
          </li>
          <li @click="execCommand('fontSize', 2)">
            <button style="font-size: 14px">2</button>
          </li>
          <li @click="execCommand('fontSize', 1)">
            <button style="font-size: 12px">1</button>
          </li>
        </ul>
      </VmEditorDropdown>
    </VmEditorButton>
    
    

    
    <VmEditorButton @click.native="execCommand('insertUnorderedList')"></VmEditorButton>

    
        <VmEditorAddimage></VmEditorAddimage>
    
    
    <VmEditorButton @click.native="execCommand('insertHorizontalRule')"></VmEditorButton>

    
    <slot></slot>
  </div>
</template>
<style lang="scss">
  .vm-editor-menu{
    width: 100%;
    box-sizing: border-box;
    display: flex;
    height: 40px;
    align-items: center;
    padding: 0 15px;
    background-color: #fafbfc;
    border-bottom: 1px solid #eeeff1;
    position: relative;
    .line{
      display: inline-block;
      width: 1px;
      height: 40px;
      margin: 0 10px;
      background-color: #eeeff1;
    }
  }
  ul.vm-editor-ul{
    padding: 0;
    margin: 0;
    li{
      margin: 0;
      padding: 6px 30px;
      display: flex;
      justify-content: center;
      &:hover{
        background: #f8f8f8;
      }
      h1{
        text-align: center;
      }
      button{
        color: inherit;
        width: 100%;
        height: 100%;
        background: transparent;
        border: none;
        cursor: pointer;
      }
    }  
  }
</style>
<script>
import VmEditorButton from './vm-editor-button.vue'
import VmEditorDropdown from './vm-editor-dropdown.vue'
import VmEditorAddimage from './vm-editor-addimage.vue'
export default {
  name: 'VmEditorMenu',
  components: {
    VmEditorButton,
    VmEditorDropdown,
    VmEditorAddimage,
  },
  methods: {
    execCommand: function (commandName, valueArgument) {
      if (!valueArgument) {
        valueArgument = null
      }
      document.execCommand(commandName, false, valueArgument)
    },
    setImage: function (evt) {
      let reader = new FileReader()
      let file = evt.target.files[0]
      reader.readAsDataURL(file)
      reader.onload = function (evt) {
        let base64Image = evt.target.result
        document.execCommand('insertImage', false, base64Image)
      }
    }
  }
}
</script>
