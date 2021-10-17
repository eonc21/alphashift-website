<template>
  <div id="more-services-page">
      <WidgetList :widgets="widgets" />
  </div>
</template>

<script>
import WidgetList from './WidgetList.vue'

export default {
    name: 'MoreServices',

    props: {
        inverted: Boolean,
    },

    components: {
        WidgetList,
    },

    data() {
            return {
                widgets: []
            }
        },

        created() {
            this.widgets = [
            {
                id: 1,
                title: `Data & AI Strategy Consulting`,
                text:  `Our extensive service lists includes data and AI 
                transformation strategy slide deck, along with use cases, 
                cases catalog and a solution vision. We first provide our
                customers with an implementation timeline and roadmap, followed
                by model assessment and analytical data reports.
                    `,
                 image: "https://res.cloudinary.com/gromceri-test/image/upload/v1634162817/AlphaShift/carlos-muza-hpjSkU2UYSU-unsplash_ybf2nq.jpg"

            },

            {
                id: 2,
                title: `Data Analytics & Management`,
                text: `Our predictive analytics services involve advanced analytics capabilities,
                spanning ad-hoc statistical and data mining.We are undoubtedly qualified
                in predictive models and content analysis. Data visualization, enterprise-wide 
                reporting and dashboarding, benchmarking and business performace management tools; 
                you name it, we have it.
                    `,
                 image: "https://res.cloudinary.com/gromceri-test/image/upload/v1634162984/AlphaShift/kelly-sikkema--nz-GTuvyBw-unsplash_mqugz3.jpg"

            },

            {
                id: 3,
                title: `AI & ML Implementation`,
                text: `Our AI services give you a glimpse into the future, allowing you to stay on the
                cutting edge of innovation and technology. From concept to implementation, we identify
                the potential for automating your business, based on prescriptive data solutions, and show you 
                how to put it to the best possible use.`,
                 image: "https://res.cloudinary.com/gromceri-test/image/upload/v1634162725/AlphaShift/mimi-thian-ZKBzlifgkgw-unsplash_eh6w0r.jpg"
            },
            ]
        }

}
</script>

<style>

#more-services-page {
    background-color: #171717;
    width: 100%;
    height: 100%;
    /* border: 1px solid salmon; */
    color: rgba(255, 255, 255, 0.849);
}

</style>