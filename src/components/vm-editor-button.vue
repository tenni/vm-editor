<template>
  <div class="vm-editor-button">
    <span class="button">
      
    </span>
    
  </div>
</template>
<style lang="scss">
  .vm-editor-button{
    position: relative;
    border-radius: 4px;
    outline: 0;
    cursor: pointer;
    background-color: transparent;
    border: none;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0 5px;
    padding: 0;
    &:first-child{
      margin-left: 0;
    }
    span.button{
      width: 24px;
      height: 24px;
      display: flex;
      justify-content: center;
      align-items: center;
      background:#000;
      &:hover{
        background-color: #eee;
      }
    }
  }
</style>
<script>
export default {
  name: 'VmEditorButton'
}
</script>
