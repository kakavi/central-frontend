<!--
Copyright 2020 ODK Central Developers
See the NOTICE file at the top-level directory of this distribution and at
https://github.com/getodk/central-frontend/blob/master/NOTICE.

This file is part of ODK Central. It is subject to the license terms in
the LICENSE file found in the top-level directory of this distribution and at
https://www.apache.org/licenses/LICENSE-2.0. No part of ODK Central,
including this file, may be copied, modified, propagated, or distributed
except according to the terms contained in the LICENSE file.
-->
<template>
  <div>
    <form-version-table @view-xml="showModal('viewXml')"/>
    <loading :state="$store.getters.initiallyLoading(['formVersions'])"/>

    <form-version-view-xml v-bind="viewXml" @hide="hideModal('viewXml')"/>
  </div>
</template>

<script>
import FormVersionTable from './table.vue';
import Loading from '../loading.vue';
import modal from '../../mixins/modal';
import validateData from '../../mixins/validate-data';
import { apiPaths } from '../../util/request';
import { loadAsyncComponent } from '../../util/async-components';
import { noop } from '../../util/util';

export default {
  name: 'FormVersionList',
  components: {
    FormVersionTable,
    FormVersionViewXml: loadAsyncComponent('FormVersionViewXml'),
    Loading
  },
  mixins: [modal({ viewXml: 'FormVersionViewXml' }), validateData()],
  props: {
    projectId: {
      type: String,
      required: true
    },
    xmlFormId: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      viewXml: {
        state: false
      }
    };
  },
  created() {
    this.fetchData();
  },
  methods: {
    fetchData() {
      this.$store.dispatch('get', [{
        // We do not reconcile `form` and `formVersions`. In the unusual case
        // that `formVersions` is empty, we still render the component.
        key: 'formVersions',
        url: apiPaths.formVersions(this.projectId, this.xmlFormId),
        extended: true,
        resend: false
      }]).catch(noop);
    }
  }
};
</script>
