<script>
import Title from './sections/Title.vue'
import Abstract from './sections/Abstract.vue'
import Markdown_experiment from './sections/Markdown_experiment.vue'
import Markdown_systemivervuew from './sections/Markdown_systemivervuew.vue'
import Markdown_conclusion from './sections/Markdown_conclusion.vue'

import Abstract_simplify from './sections/Abstract_simplify.vue'
import Markdown_experiment_simplify from './sections/Markdown_experiment_simplify.vue'
import Markdown_systemivervuew_simplify from './sections/Markdown_systemivervuew_simplify.vue'
import Markdown_conclusion_simplify from './sections/Markdown_conclusion_simplify.vue'

import Video from './sections/Video.vue'
import more_video from './sections/more_video.vue'

import BibTeX from './sections/BibTeX.vue'
import Carousel from './sections/Carousel.vue'
import ImageSlider from './sections/ImageSlider.vue'
import ImageSliderInner from './sections/ImageSliderInner.vue'
import ImageSelector from './sections/ImageSelector.vue'
import Echart from './sections/Echart.vue'
import Table from './sections/Table.vue'
import Collapse from './sections/Collapse.vue'
import SeletionForComparison from './sections/SeletionForComparison.vue'
import Comment from './sections/Comment.vue'
import Latex from './sections/Latex.vue'
import systemoverview_latex from './sections/systemoverview_latex.vue'
import Model3D from './sections/Model3D.vue'
import GaussianSplats3D from './sections/GaussianSplats3D.vue'

export default {
  components: {
    Title,
    Video,

    Abstract,
    Markdown_systemivervuew,
    Markdown_experiment,
    Markdown_conclusion,

    Abstract_simplify,
    Markdown_systemivervuew_simplify,
    Markdown_experiment_simplify,
    Markdown_conclusion_simplify,
    more_video,
  }
}
</script>

<template>
  <Title/>
  <!-- <Carousel/> -->
  <!-- <Video/> -->

  <!-- <Abstract/>
  <systemoverview_latex/>
  <Markdown_systemivervuew/>
  <Markdown_experiment/> -->

  <Abstract_simplify/>
  <systemoverview_latex_simplify/>
  <Markdown_systemivervuew_simplify/>
  <Markdown_experiment_simplify/>
  
  <more_video/>

  <Markdown_conclusion_simplify/>
  <!-- <Markdown_conclusion/> -->
</template>