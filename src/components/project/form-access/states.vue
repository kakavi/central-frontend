<!--
Copyright 2019 ODK Central Developers
See the NOTICE file at the top-level directory of this distribution and at
https://github.com/getodk/central-frontend/blob/master/NOTICE.

This file is part of ODK Central. It is subject to the license terms in
the LICENSE file found in the top-level directory of this distribution and at
https://www.apache.org/licenses/LICENSE-2.0. No part of ODK Central,
including this file, may be copied, modified, propagated, or distributed
except according to the terms contained in the LICENSE file.
-->
<template>
  <modal id="project-form-access-states" :state="state" hideable backdrop
    @hide="$emit('hide')">
    <template #title>{{ $t('title') }}</template>
    <template #body>
      <div class="modal-introduction">
        <p>{{ $t('introduction[0]') }}</p>
        <i18n tag="p" path="introduction[1].full">
          <template #open>
            <strong>{{ $t('introduction[1].open') }}</strong>
          </template>
        </i18n>
        <i18n tag="p" path="introduction[2].full">
          <template #closing>
            <strong>{{ $t('introduction[2].closing') }}</strong>
          </template>
          <template #not>
            <em>{{ $t('introduction[2].not') }}</em>
          </template>
        </i18n>
        <i18n tag="p" path="introduction[3].full">
          <template #closed>
            <strong>{{ $t('introduction[3].closed') }}</strong>
          </template>
          <template #not1>
            <em>{{ $t('introduction[3].not1') }}</em>
          </template>
          <template #not2>
            <em>{{ $t('introduction[3].not2') }}</em>
          </template>
        </i18n>
      </div>
      <div class="modal-actions">
        <button type="button" class="btn btn-primary" @click="$emit('hide')">
          {{ $t('action.ok') }}
        </button>
      </div>
    </template>
  </modal>
</template>

<script>
import Modal from '../../modal.vue';

export default {
  name: 'ProjectFormAccessStates',
  components: { Modal },
  props: {
    state: {
      type: Boolean,
      default: false
    }
  }
};
</script>

<style lang="scss">
#project-form-access-states {
  .modal-introduction p:first-child {
    margin-bottom: 20px;
  }
}
</style>

<i18n lang="json5">
{
  "en": {
    // This is the title at the top of a pop-up.
    "title": "Form States",
    "introduction": [
      "Form States control the lifecycle state of each Form. Usually, but not always, a Form will start Open and proceed through Closing to Closed when it is no longer needed.",
      {
        "full": "{open} Forms are available to download on mobile devices, and will accept new Submissions.",
        "open": "Open"
      },
      {
        "full": "{closing} Forms will accept new Submissions, but are {not} available to download on mobile devices.",
        "closing": "Closing",
        "not": "not"
      },
      {
        "full": "{closed} Forms are {not1} available to download on mobile devices, and will {not2} accept new Submissions.",
        "closed": "Closed",
        "not1": "not",
        "not2": "not"
      }
    ]
  }
}
</i18n>

<!-- Autogenerated by destructure.js -->
<i18n>
{
  "cs": {
    "title": "Stavy formuláře",
    "introduction": [
      "Stavy formuláře kontrolují stav životního cyklu každého formuláře. Obvykle, ale ne vždy, bude formulář otevřen a bude pokračovat přes Uzavření až do Uzavřeno, pokud již nebude potřeba.",
      {
        "full": "{open} formuláře jsou k dispozici ke stažení na mobilních zařízeních a budou přijímat nové příspěvky.",
        "open": "Otevřené"
      },
      {
        "full": "{closing} formuláře přijímají nové příspěvky, ale {not} k dispozici ke stažení na mobilních zařízeních.",
        "closing": "Uzavřené",
        "not": "nejsou"
      },
      {
        "full": "{closed} formuláře {not1}jsou k dispozici ke stažení na mobilních zařízeních a {not2}přijímají nová podání.",
        "closed": "Uzavřené",
        "not1": "ne",
        "not2": "ne"
      }
    ]
  },
  "de": {
    "title": "Formular-Status",
    "introduction": [
      "Formular-Status steuern den Lebenszyklusstatus eines jeden Formulars. Normalerweise, aber nicht immer, beginnt ein Formular im Status Offen und geht weiter über Schließen nach Geschlossen, wenn es nicht mehr benötigt wird.",
      {
        "full": "{open} Formulare können auf mobile Geräte heruntergeladen werden und akzeptieren neue Übermittlungen.",
        "open": "Offen"
      },
      {
        "full": "{closing} Formulare akzeptieren neue Übermittlungen, aber können {not} auf mobile Geräte heruntergeladen werden.",
        "closing": "Wird geschlossen",
        "not": "nicht"
      },
      {
        "full": "{closed} Formulare können {not1} auf mobile Geräte heruntergeladen werden und akzeptieren {not2} neuen Übermittlungen.",
        "closed": "Geschlossene",
        "not1": "nicht",
        "not2": "nicht"
      }
    ]
  },
  "es": {
    "title": "Estado del formulario",
    "introduction": [
      "El estado del formulario controla el ciclo de vida de cada formulario. Por lo general, pero en algunas ocasiones no será de este modo, el formulario comenzará abierto y luego procederá a cerrarse cuando ya no sea necesario.",
      {
        "full": "Los formularios {open} están disponibles para descarga en dispositivos móviles y aceptán nuevos envíos.",
        "open": "abiertos"
      },
      {
        "full": "Los formularios {closing} aceptán nuevos envíos pero {not} están disponibles para descarga en dispositivos móviles.",
        "closing": "cerrando",
        "not": "no"
      },
      {
        "full": "Los formularios {closed} {not1} están disponibles para descarga en dispositivos móviles, y {not2} aceptán nuevos envíos.",
        "closed": "cerrados",
        "not1": "no",
        "not2": "no"
      }
    ]
  },
  "fr": {
    "title": "États des formulaires",
    "introduction": [
      "Les États de formulaire contrôlent le cycle de vie de chaque formulaire. Généralement, mais pas toujours, un formulaire démarrera \"Ouvert\", sera utilisé jusqu'à sa \"Fermeture\", et sera \"Fermé\" quand il ne sera plus utile.",
      {
        "full": "Les formulaires {open} sont téléchargeables sur les appareils mobiles, et peuvent accepter des soumissions.",
        "open": "Ouvert"
      },
      {
        "full": "Les formulaires {closing} acceptent les nouvelles soumissions, mais ne sont {not} disponibles en téléchargement sur les appareils mobiles.",
        "closing": "Fermeture",
        "not": "pas"
      },
      {
        "full": "Les formulaires {closed} ne sont {not1} disponibles en téléchargement sur les appareils mobiles, et n'accepteront {not2} de nouvelles soumissions.",
        "closed": "Fermé",
        "not1": "pas",
        "not2": "pas"
      }
    ]
  },
  "id": {
    "title": "Status Formulir",
    "introduction": [
      "Status Formulir mengontrol keadaan lingkar keaktifan setiap formulir. Biasanya, tidak selalu, sebuah formulir akan dimulai dengan status Terbuka, kemudian Penutupan, hingga Ditutup, ketika sudah tidak diperlukan lagi.",
      {
        "full": "Formulir {open} tersedia untuk diunduh lewat perangkat seluler dan akan menerima kiriman data baru.",
        "open": "Terbuka"
      },
      {
        "full": "{closing} Formulir akan menerima kiriman data baru, tetapi {not} tersedia untuk diunduh di perangkat seluler.",
        "closing": "Penutupan",
        "not": "tidak"
      },
      {
        "full": "Formulir {closed} {not1} tersedia untuk diunduh di perangkat seluler dan {not2} menerima kiriman data baru.",
        "closed": "Ditutup",
        "not1": "tidak",
        "not2": "tidak"
      }
    ]
  }
}
</i18n>
