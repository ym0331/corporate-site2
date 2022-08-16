<template>
  <div>
    <CarouselView />
    <!-- <v-img src="/img/piano.jpg"></v-img> -->
    <transition-group tag="ul" name="list">
      <li v-for="content in contents" :key="content" :id="content">
        <!-- <div v-motion-pop-visible> -->
        <div>
          <h2><p class="is-big">{{ content.name2 }}</p><p class="is-small">{{ content.name }}</p></h2>
          <component :is="content.name"></component>
        </div>
      </li>
    </transition-group>
  </div>
</template>

<script>
import CarouselView from "@/components/parts/CarouselView.vue";

import Access from "@/components/parts/AcessArea.vue";
// import School from "@/components/parts/SchoolArea.vue";
import business from "@/components/parts/TeacherArea.vue";
// import Lesson from "@/components/parts/LessonArea.vue";
import News from "@/components/parts/NewsArea.vue";
export default {
  name: "MainContents",
  components: {
    // School,
    business,
    // Lesson,
    Access,
    CarouselView,
    News
  },
  data() {
    return {
      visible: false,
      contents: [
        // "School",
        {name:"business", name2:"事業内容"},
        // "Lesson",
        {name:"Access", name2:"アクセス"},
        {name:"News", name2:"新着情報"}
      ]
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h2 {
  font-size: 1.6rem;
  margin-bottom: 10px;
  display: flex;
  align-items: baseline;
  width: 80%;
}

.is-big {
  margin-right: 10px;
}

.is-small {
  font-size: 0.6em;
  color: #143265;
}
</style>
