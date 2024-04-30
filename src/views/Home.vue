<template>
  <div class="container">
    <MatrixContainer :users="users" :skills="skills">
      <template #evaluation="{ userId, skillId }"> {{ getUserName(userId) }} {{ getSkillName(skillId) }} </template>
    </MatrixContainer>
  </div>
</template>

<script setup lang="ts">
import MatrixContainer from '@/components/MatrixContainer.vue';

interface User {
  id: number;
  name: string;
}

interface Skill {
  id: number;
  name: string;
}

const users: User[] = [
  { id: 1, name: 'サミュエル・ベケット' },
  { id: 2, name: '田中 太郎' },
  { id: 3, name: '木村 権三郎衛門' },
  { id: 4, name: 'ジョン・スミス' },
  { id: 5, name: '山田 花子' },
  { id: 6, name: 'ジェーン・ドー' },
  { id: 7, name: '山本 一郎' },
  { id: 8, name: '山田 二郎' },
  { id: 9, name: '山本 三郎' },
  { id: 10, name: '山田 四郎' },
  { id: 11, name: '山本 五郎' },
  { id: 12, name: '山田 六郎' },
  { id: 13, name: '山本 七郎' },
  { id: 14, name: '山田 八郎' },
  { id: 15, name: '山本 九郎' },
  { id: 16, name: '山田 十郎' },
  { id: 17, name: '山本 十一郎' },
  { id: 18, name: '山田 十二郎' },
  { id: 19, name: '山本 十三郎' },
  { id: 20, name: '山田 十四郎' },
  { id: 21, name: '山本 十五郎' },
  { id: 22, name: '山田 十六郎' },
  { id: 23, name: '山本 十七郎' },
  { id: 24, name: '山田 十八郎' },
  { id: 25, name: '山本 十九郎' },
  { id: 26, name: '山田 二十郎' },
  { id: 27, name: '山本 二十一郎' },
  { id: 28, name: '山田 二十二郎' }
];

const skills: Skill[] = [
  { id: 1, name: 'JavaScript' },
  { id: 2, name: 'TypeScript' },
  { id: 3, name: 'Ruby' },
  { id: 4, name: 'Python' },
  { id: 5, name: 'Java' },
  { id: 6, name: 'C#' },
  { id: 7, name: 'C++' },
  { id: 8, name: 'PHP' },
  { id: 9, name: 'Go' },
  { id: 10, name: 'Swift' },
  { id: 11, name: 'Kotlin' },
  { id: 12, name: 'Rust' },
  { id: 13, name: 'Scala' },
  { id: 14, name: 'Perl' },
  { id: 15, name: 'Haskell' },
  { id: 16, name: 'Lua' },
  { id: 17, name: 'R' },
  { id: 18, name: 'Objective-C' },
  { id: 19, name: 'Dart' },
  { id: 20, name: 'Shell' },
  { id: 21, name: 'PowerShell' },
  { id: 22, name: 'SQL' },
  { id: 23, name: 'HTML' },
  { id: 24, name: 'CSS' },
  { id: 25, name: 'Sass' },
  { id: 26, name: 'Less' },
  { id: 27, name: 'Stylus' },
  { id: 28, name: 'Vue.js' },
  { id: 29, name: 'React' },
  { id: 30, name: 'Angular' },
  { id: 31, name: 'Node.js' },
  { id: 32, name: 'Express' },
  { id: 33, name: 'NestJS' },
  { id: 34, name: 'Ruby on Rails' },
  { id: 35, name: 'Django' },
  { id: 36, name: 'Flask' },
  { id: 37, name: 'Spring' },
  { id: 38, name: 'Laravel' },
  { id: 39, name: 'Symfony' }
];

const getUserName = (userId: number) => users.find(user => user.id === userId)?.name;

const getSkillName = (skillId: number) => skills.find(skill => skill.id === skillId)?.name;

</script>

<style lang="scss" scoped></style>
