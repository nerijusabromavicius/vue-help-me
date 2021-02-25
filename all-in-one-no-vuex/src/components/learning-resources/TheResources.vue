<template>
  <BaseCard>
    <BaseButton
      @click="setSelectedTab('StoredResources')"
      :mode="storedSelected"
      >Stored Resources</BaseButton
    >
    <BaseButton @click="setSelectedTab('AddResource')" :mode="addSelected"
      >Add Resource</BaseButton
    >
  </BaseCard>
  <keep-alive>
    <component :is="selectedTab"></component>
  </keep-alive>
</template>

<script>
import StoredResources from './StoredResources';
import AddResource from './AddResource';
export default {
  components: {
    StoredResources,
    AddResource
  },
  data() {
    return {
      selectedTab: 'StoredResources',
      learningResources: [
        {
          id: 'official-guide',
          title: 'Official guide',
          description: 'Official Vue.js documentation',
          link: 'https://www.vuejs.org'
        },
        {
          id: 'google',
          title: 'Google',
          description: 'Google it',
          link: 'https://www.google.com'
        }
      ]
    };
  },
  provide() {
    return {
      resources: this.learningResources,
      addResource: this.addResource,
      removeResource: this.removeResource
    };
  },
  computed: {
    storedSelected() {
      return this.selectedTab === 'StoredResources' ? null : 'flat';
    },
    addSelected() {
      return this.selectedTab === 'AddResource' ? null : 'flat';
    }
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
    addResource(title, description, url) {
      const newResource = {
        id: new Date().toISOString,
        title: title,
        description: description,
        link: url
      };
      this.learningResources.unshift(newResource);
      this.selectedTab = 'StoredResources';
    },
    removeResource(id) {
      this.learningResources.splice(id, 1);
    }
  }
};
</script>

<style scoped></style>
