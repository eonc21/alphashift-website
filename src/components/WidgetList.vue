<template>
    <div class="widget-list">
        <animated-component>
            <div class="widget" >
                <HorizontalWidget :widget="widgets[0]" />

            </div>
        </animated-component>

        <animated-component>

        <div class="widget" >
            <InvertedWidget :widget="widgets[1]" />

        </div>
        </animated-component>


        <animated-component>

        <div class="widget" >
            <HorizontalWidget :widget="widgets[2]" />

        </div>
        </animated-component>

    </div>
        
  
</template>

<script>
import HorizontalWidget from "../components/HorizontalWidget.vue"
import InvertedWidget from "../components/InvertedWidget.vue"
import AnimatedComponent from '../components/AnimatedComponent.vue'

export default {
    name: 'WidgetList',


    props: {
        widgets: Array,
    },

    components: {
        HorizontalWidget,
        InvertedWidget,
        AnimatedComponent,
    }

}
</script>

<style>

.widget-list {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-self: center;
}

.widget {
    margin: 9vh 0;
    display: flex;
    align-self: center;
    justify-content: center;
}

@media (max-width: 600px) {

    .widget {
        margin: 3vh 0;
    }
    
}



</style>