<template>
  <el-container>
    <el-header>
      <game-control @startGame="clickStartGame" :BombNumberControl='BombNumberControlIndex' ></game-control>
    </el-header>
    <el-main>
      <game-main :gameData="gameDataFromIndex " @BombNumber='BombNumberIndex' ></game-main>
    </el-main>
  </el-container>
</template>

<script>
import gameControl from '@/views/components/gameControl';
import gameMain from '@/views/components/gameMain';

export default {
  name: 'App',
  data(){//储存数据
    return {
      gameDataFromIndex: {},
      BombNumberControlIndex:10,
     
    };
  },
  methods: {//储存方法
    clickStartGame(params){
      console.log(params,123);
      this.gameDataFromIndex = params;
    },

    BombNumberIndex(params){
      console.log(params,444);
      console.log( typeof(params));
      this.BombNumberControlIndex=params;
      console.log(this.BombNumberControlIndex);
    },
  },
  components: {//注册组建
    gameControl,
    gameMain,
  },
}
</script>

<style lang="scss">
.el-header{
  display: flex;
  background: #ccc;
  align-items: center;
  justify-content: center;
}
</style>
