<template>
  <section class="secondary-card container keyrates">
    <h3>{{ $t("message.keyrates_title") }}</h3>
    <table class="align-center color-light">
      <tr>
        <td>{{ $t("message.keyrates_header_col1") }}</td>
        <td>{{ $t("message.keyrates_header_col2") }}</td>
        <td>{{ $t("message.keyrates_header_col3") }}</td>
      </tr>
    </table>
    <div v-for="(item) in settings.keyrates" v-bind:key="item.name" v-bind:title="item.name">
      <h4>{{ $t("message." + item.name )}}</h4>
      <table class="align-center color-light">
        <tr>
          <td>
            <i v-if="item.trend==='green'" class="pi pi-arrow-up pi-success"></i>
            <i v-if="item.trend==='red'" class="pi pi-arrow-down pi-error"></i>
            {{ item.current }}
          </td>
          <td>{{ item.high }}</td>
          <td>{{ item.low }}</td>
        </tr>
      </table>
    </div>
  </section>
</template>

<script>
import { mainconfig } from '../../global';

export default {
  data() {
    return mainconfig;
  },
};
</script>
