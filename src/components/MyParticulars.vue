<template>
  <div class="my-particular">
    <h2 class="heading">Personal Particulars</h2>
    <hr class="divider" />
    <div class="fields-container">
      <div class="field full-width">
        <label>Nationality</label>
        <select>
          <option value="country1">Pakistan</option>
          <option value="country2">United States</option>
        </select>
      </div>
      <div class="field half-width">
        <label>Marital Status</label>
        <select>
          <option value="single">Single</option>
          <option value="married">Married</option>
        </select>
      </div>
      <div class="field half-width">
        <label>Age:</label>
        <input type="range"  min="0" max="100" step="1" value="50" />
      </div>
      <div class="field half-width">
        <label>Employment</label>
        <select>
          <option value="employed">Employed</option>
          <option value="unemployed">Unemployed</option>
        </select>
      </div>
      <div class="field half-width">
        <label>Income Range:</label>
        <input type="range"  min="0" max="100" step="1" value="50" />
      </div>
      <div class="field full-width">
        <label>Ownership History</label>
        <select>
          <option value="owned">Owned</option>
          <option value="rented">Rented</option>
        </select>
      </div>
      <div class="field checkboxes">
        <label class="family-label">Family Nucleus</label>
        <div class="checkbox-list">
          <label>
            <input type="checkbox"> Orphaned siblings
          </label>
          <label>
            <input type="checkbox"> Married couples and/or parent(s) with child(ren)
          </label>
          <label>
            <input type="checkbox"> Multi-generation families
          </label>
          <label>
            <input type="checkbox"> Orphaned sibling(s)
          </label>
          <label>
            <input type="checkbox"> Families with non-residents
          </label>
          <label>
            <input type="checkbox"> Others
          </label>
        </div>
      </div>
      <div class="buttons">
        <button class="cancel-button">Cancel</button>
        <button class="update-button">Update</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.my-particular {
  margin: 0 auto; 
  padding: 15px;
  background-color: #ededed;
  width: 508px;
  height: 685px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

.fields-container {
  padding: 10px;
  width: 100%;
  height: auto;
  background-color: #ffff;
  box-shadow: inset 3px 0 8px -5px #d8d6d6, inset -3px 0 8px -5px #d8d6d6;
}
.heading {
  color: #1f0567;
  margin-bottom: 10px;
}

.divider {
  border: none;
  border-top: 2px solid #ccc;
  width: 100%;
  margin-top: 10px;
}

.field {
  display: flex;
  flex-wrap: wrap;
  border-radius: 5px;
  margin-bottom: 10px;
}

.full-width {
  width: 100%;
}

.half-width {
  width: calc(50% - 10px);
}

label {
  font-weight: bold;
  align-self: flex-start;
}

select,
input[type="range"] {
  width: 100%;
  padding: 5px;
  border: 1px solid #1f0567;
  border-radius: 5px;
}
.checkboxes {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.checkbox-list {
  margin-left: 10px;
  justify-items: start;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.buttons {
  display: flex;
  justify-content: flex-end;
  margin-top: 20px;
}

.cancel-button,
.update-button {
  background-color: #ccc;
  color: #fff;
  padding: 10px 25px;
  border: none;
  border-radius: 20px;
  margin-right: 10px;
}

.update-button {
  background-color: #1f0567;
}
</style>
