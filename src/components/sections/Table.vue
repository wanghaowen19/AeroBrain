<script lang="ts" setup>

// 表格数据 - TABLE I
const tableData1 = [
  { method: 'Random', TL: '32.78', NE: '3.20', SR: '11.11', CR: '66.67', SPL: '5.67' },
  { method: 'VisualGLM [25]', TL: '29.21', NE: '3.29', SR: '54.26', CR: '36.17', SPL: '36.13' },
  { method: 'MiniGPT-4 [26]', TL: '31.15', NE: '3.31', SR: '55.56', CR: '31.48', SPL: '34.50' },
  { method: 'MiniGPT-v2 [27]', TL: '28.65', NE: '2.92', SR: '53.57', CR: '29.76', SPL: '41.16' },
  { method: 'Instruct-Nav [18]', TL: '20.26', NE: '3.25', SR: '61.67', CR: '31.67', SPL: '52.90' },
  { method: 'AeroBrain (ours)', TL: '20.82', NE: '2.87', SR: '75.93', CR: '16.67', SPL: '58.78' }
];

// 表格数据 - TABLE II
const tableData2 = [
  { combination: 'Llama3.3 70B + Llama3.2 11B', TL: '37.24', NE: '3.06', SR: '40.91', CR: '59.09', SPL: '17.05' },
  { combination: 'DeepSeek-V3 + Qwen2-VL 72B', TL: '21.66', NE: '3.30', SR: '65.22', CR: '34.78', SPL: '53.60' },
  { combination: 'GPT-3.5 + GPT-4o', TL: '21.24', NE: '2.87', SR: '66.67', CR: '29.17', SPL: '51.71' },
  { combination: 'DeepSeek-V3 + GPT-4o (ours)', TL: '20.82', NE: '2.87', SR: '75.93', CR: '16.67', SPL: '58.78' }
];

// 表格数据 - TABLE III
const tableData3 = [
  { method: 'w/o path planning', TL: '27.94', NE: '3.10', SR: '26.67', CR: '46.67', SPL: '21.26' },
  { method: 'Fast-Planner [28]', TL: '26.16', NE: '3.35', SR: '47.06', CR: '29.41', SPL: '30.96' },
  { method: 'Ego-Planner [29]', TL: '23.19', NE: '3.27', SR: '56.25', CR: '18.75', SPL: '39.15' },
  { method: 'Ego-Swarm (N = 1) [30]', TL: '22.95', NE: '3.63', SR: '53.85', CR: '15.38', SPL: '39.87' },
  { method: 'PPO [31]', TL: '21.57', NE: '2.89', SR: '73.21', CR: '17.86', SPL: '58.33' },
  { method: 'DDPG [32]', TL: '22.60', NE: '2.84', SR: '72.92', CR: '18.75', SPL: '53.28' },
  { method: 'SAC (ours)', TL: '20.82', NE: '2.87', SR: '75.93', CR: '16.67', SPL: '58.78' }
];

// 表格数据 - TABLE IV
const tableData4 = [
  { method: 'AeroBrain', TL: '20.82', NE: '2.87', SR: '75.93', CR: '16.67', SPL: '58.78' },
  { method: 'w/o PP', TL: '20.98', NE: '2.90', SR: '68.75', CR: '26.56', SPL: '48.62' },
  { method: 'w/o PT', TL: '22.09', NE: '2.99', SR: '51.72', CR: '34.48', SPL: '37.50' },
  { method: 'w/o PT and PP', TL: '26.86', NE: '3.15', SR: '56.04', CR: '24.18', SPL: '21.83' }
];
</script>

<template>
    <div>
        <el-divider />

        <el-row justify="center">
            <h1 class="section-title">Performance Comparison of UAV Navigation Algorithms</h1>
        </el-row>

        <el-row justify="center">
            <h2 class="section-subtitle">Comparison of Different Methods and Models</h2>
        </el-row>
        
        <!-- 数据表格 -->
        <el-row justify="center">
            <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">

                <!-- 卡片 -->
                <el-card class="card">

                    <!-- 默认tab -->
                    <el-tabs class="demo-tabs" model-value="TABLE I">

                    <!-- TABLE I -->
                    <el-tab-pane label="TABLE I" name="TABLE I">
                        <el-table :data="tableData1" style="width: 100%" border>
                            <el-table-column prop="method" label="Methods" min-width="180" sortable/>
                            <el-table-column prop="TL" label="TL ↓" min-width="100" sortable/>
                            <el-table-column prop="NE" label="NE ↓" min-width="100" sortable/>
                            <el-table-column prop="SR" label="SR ↑" min-width="100" sortable/>
                            <el-table-column prop="CR" label="CR ↓" min-width="100" sortable/>
                            <el-table-column prop="SPL" label="SPL ↑" min-width="100" sortable/>
                        </el-table>
                    </el-tab-pane>

                    <!-- TABLE II -->
                    <el-tab-pane label="TABLE II" name="TABLE II">
                        <el-table :data="tableData2" style="width: 100%" border>
                            <el-table-column prop="combination" label="Large Models Combination" min-width="300" sortable/>
                            <el-table-column prop="TL" label="TL ↓" min-width="100" sortable/>
                            <el-table-column prop="NE" label="NE ↓" min-width="100" sortable/>
                            <el-table-column prop="SR" label="SR ↑" min-width="100" sortable/>
                            <el-table-column prop="CR" label="CR ↓" min-width="100" sortable/>
                            <el-table-column prop="SPL" label="SPL ↑" min-width="100" sortable/>
                        </el-table>
                    </el-tab-pane>

                    <!-- TABLE III -->
                    <el-tab-pane label="TABLE III" name="TABLE III">
                        <el-table :data="tableData3" style="width: 100%" border>
                            <el-table-column prop="method" label="Path Planning Alg. in AeroBrain" min-width="300" sortable/>
                            <el-table-column prop="TL" label="TL ↓" min-width="100" sortable/>
                            <el-table-column prop="NE" label="NE ↓" min-width="100" sortable/>
                            <el-table-column prop="SR" label="SR ↑" min-width="100" sortable/>
                            <el-table-column prop="CR" label="CR ↓" min-width="100" sortable/>
                            <el-table-column prop="SPL" label="SPL ↑" min-width="100" sortable/>
                        </el-table>
                    </el-tab-pane>

                    <!-- TABLE IV -->
                    <el-tab-pane label="TABLE IV" name="TABLE IV">
                        <el-table :data="tableData4" style="width: 100%" border>
                            <el-table-column prop="method" label="Methods" min-width="200" sortable/>
                            <el-table-column prop="TL" label="TL ↓" min-width="100" sortable/>
                            <el-table-column prop="NE" label="NE ↓" min-width="100" sortable/>
                            <el-table-column prop="SR" label="SR ↑" min-width="100" sortable/>
                            <el-table-column prop="CR" label="CR ↓" min-width="100" sortable/>
                            <el-table-column prop="SPL" label="SPL ↑" min-width="100" sortable/>
                        </el-table>
                    </el-tab-pane>

                    </el-tabs>

                </el-card>
            </el-col>
        </el-row>
    </div>
</template>

<style scoped>
.card {
    margin-top: 20px;
}
.section-subtitle {
    font-size: 18px;
    color: #555;
    margin-bottom: 20px;
}
</style>
