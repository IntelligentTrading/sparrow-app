<template>
  <div>
    <el-row style="padding:20px">
      <label class="investment-label">Recurring</label>
    </el-row>
    <el-row>
      <el-input class="biginput" placeholder="0.00">
        <template slot="prepend">$</template>
      </el-input>
    </el-row>
    <el-row style="padding:20px">
      <el-button
        class="suggestion"
        round
        v-for="suggestion in suggestions"
        :key="suggestion"
      >$ {{suggestion}}</el-button>
    </el-row>
    <el-row>
      <el-select style="margin:10px" v-model="frequency" placeholder="Schedule investment">
        <el-option
          v-for="item in frequencies"
          :key="item.placeholder"
          :label="item.placeholder"
          :value="item"
        ></el-option>
      </el-select>
      <el-select style="margin:10px" v-model="moment" :placeholder="this.frequency.placeholder">
        <el-option v-for="item in this.frequency.moments" :key="item" :label="item" :value="item"></el-option>
      </el-select>
    </el-row>
    <el-button class="stop" round>Stop recurring</el-button>
    <el-button class="invest" round>Update</el-button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      suggestions: [5, 25, 50, 100],
      frequencies: [
        { placeholder: "Daily", moments: ["00:00", "06:00", "12:00"] },
        {
          placeholder: "Weekly",
          moments: ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"]
        }
      ],
      frequency: "",
      moment: ""
    };
  }
};
</script>

<style>
.stop {
  color: red;
  border: transparent;
}

.stop:hover {
  color: tomato;
  background: transparent;
}
.stop:focus {
  background: transparent;
  color: red;
}

.suggestion {
  background: lightgray;
  width: 80px;
}

.biginput .el-input__inner {
  border: transparent;
  height: 100px !important;
  font-weight: 100;
  font-size: 72px;
  color: cornflowerblue;
  text-align: left;
}
.biginput .el-input-group__prepend {
  border: transparent;
  font-size: 42px;
  background: transparent;
  vertical-align: middle;
  color: cornflowerblue;
}

.biginput {
  width: 300px;
}
</style>