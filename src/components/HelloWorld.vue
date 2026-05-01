<template>
  <div class="container">
    <h2>Solar Bill Calculator</h2>

    <!-- Current Readings -->
    <div class="section">
      <h3>Current Readings</h3>
      <p>Import</p>
      <input v-model.number="currentImport" type="number" placeholder="Current Import" />
      <p>Export</p>
      <input v-model.number="currentExport" type="number" placeholder="Current Export" />
    </div>

    <!-- Previous Readings -->
    <div class="section">
      <h3>Previous Readings</h3>
      <p>Import</p>
      <input v-model.number="previousImport" type="number" placeholder="Previous Import" />
      <p>Export</p>
      <input v-model.number="previousExport" type="number" placeholder="Previous Export" />
    </div>

    <!-- Results -->
    <div class="results">
      <h3>Results</h3>
      <p>Import Difference: {{ importDiff }}</p>
      <p>Export Difference: {{ exportDiff }}</p>
      <p><strong>Net Units (Import - Export): {{ netUnits }}</strong></p>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      currentImport: 0,
      currentExport: 0,
      previousImport: 0,
      previousExport: 0,
    };
  },
  computed: {
    importDiff() {
      return this.currentImport - this.previousImport;
    },
    exportDiff() {
      return this.currentExport - this.previousExport;
    },
    netUnits() {
      return this.importDiff - this.exportDiff;
    },
  },
};
</script>

<style scoped>
.container {
  max-width: 400px;
  margin: auto;
  font-family: Arial, sans-serif;
}

.section {
  margin-bottom: 20px;
}

input {
  display: block;
  margin: 5px 0;
  padding: 8px;
  width: 100%;
}

.results {
  background: #f5f5f5;
  padding: 10px;
  border-radius: 8px;
}
</style>