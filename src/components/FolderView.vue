<template>
    <div class="folder-files">
        <div class="folder-icon">
            <span class="material-icons">folder</span>
            <p class="folder">{{name}}</p>
        </div>
        <div class="wrap-folder">
            <template v-for="folder in folders">
                                        <FolderView :name="folder.name" :folders="folder.folders" :files="folder.files"/>
</template>
        </div>
        <div class="row-file">
<template v-for="file in files">
    <FileView :name="file.name" />
</template>
        </div>

  </div>
</template>

<script>
import FileView from "./FileView";
export default {
    name: 'FolderView',
    components: { FileView },
    props: {
        name: String,
        folders: Array,
        files: Array
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.folder {
    color: orangered;
    word-wrap: break-word;
    margin: 0;
}

.folder-files {
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    width: 100%;
    >.row-file {
        display: flex;
    }
}

.wrap-folder {
    display: flex;
    flex-flow: row;
    .folder-files {
        position: relative;
        &::before {
            position: absolute;
            content: '';
            width: 100%;
            height: 1px;
            top: 0;
            left: 0;
            background-color: #ccc;
        }
    }
}

.wrap-folder {
    width: 100%;
    .folder-files {
        .wrap-folder {
            &::after {
                    position: absolute;
                    content: '';
                    width: 100%;
                    bottom: 0;
                    height: 1px;
                    left: 0;
                    background-color: #ccc;
                }
            .folder-files {
                &:first-child {
                    &::after {
                        position: absolute;
                        content: '';
                        top: 0;
                        right: 0;
                        width: 1px;
                        height: 100%;
                        background-color: #ccc;
                    }
                }
                .row-file {
                    max-height: 0;
                    transition: max-height 0.75s ease-out;
                    transition-delay: .4s;
                    overflow: hidden;
                }
                &:hover {
                    .row-file {
                        max-height: 150px;
                        transition: max-height 0.25s ease-in;
                        transition-delay: .1s;
                    }
                }
                
            }
        }
    }
}

.row-file {
    flex-flow: row wrap;
    justify-content: space-around;
    align-items: flex-start;
    text-align: center;
    width: 100%;
    
    .file-icons {
        margin: 10px 0;
        width: 22%;
    }
}

.folder-icon {
    position: relative;
    display: flex;
    flex-flow: column;
    text-align: center;
    cursor: pointer;
    transition: linear .2s;
    width: max-content;
    &:focus,
    &:active,
    &:hover {
        background: #35c0fc;
        opacity: 0.7;
    }
    >span {
        color: #ffbf00;
        font-size: 7vw;
        display: block;
    }
}
</style>
