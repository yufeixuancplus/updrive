<template>
  <div class="layout-body">
    <!-- <list /> -->
    <router-view name="body"></router-view>
    <!-- 改变key，可以触发 created 生命周期  -->
    <rename-file :key="modal.renameFile.oldPath" />
    <file-progress />
    <create-folder />
    <domain-setting />
    <format-url />
  </div>
</template>

<script>
import { mapState } from 'vuex'

import CreateFolder from '@/views/modal/CreateFolder'
import RenameFile from '@/views/modal/RenameFile'
import FileProgress from '@/views/modal/FileProgress'
import DomainSetting from '@/views/modal/DomainSetting'
import FormatUrl from '@/views/modal/FormatUrl'

export default {
  name: 'LayoutBody',
  components: {
    CreateFolder,
    RenameFile,
    FileProgress,
    DomainSetting,
    FormatUrl,
  },
  computed: {
    ...mapState(['modal']),
  },
}
</script>