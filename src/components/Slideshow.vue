<template>
    <div>
        <div id="slideshow">
            
            <img id="1" :style="activeSlide == 1 ? {'display': 'block'} : {'display': 'none'}" class="slide" src="@/assets/vue-logo.png">
            <img id="2" :style="activeSlide == 2 ? {'display': 'block'} : {'display': 'none'}" class="slide" src="@/assets/geeks-logo.png">
            <!-- <div id="3" :style="activeSlide == 3 ? {'display': 'block'} : {'display': 'none'}" class="video-container slide">
                <iframe src="https://www.youtube.com/embed/cP9bhEknW_g" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
            </div> -->
            <video id="3" :style="activeSlide == 3 ? {'display': 'block'} : {'display': 'none'}" class="slide" src="@/assets/Vue CLI 3 Everything you need to know.mp4" poster="@/assets/Vue CLI thumbnail.jpg" controls></video>
        </div>
        <div id="buttons">
            <button id="prev" @click="activeSlide--; if(activeSlide==0){activeSlide=3}" >&lt;</button>
            <button id="next" @click="activeSlide = (activeSlide)%3; activeSlide++;" >&gt;</button>
        </div>
    </div>
    
</template>


<style scoped lang="less">
#buttons{
    width: 60%;
    margin: 1% auto;
    display: flex;
    justify-content: space-between;
}
button {
    width: 10%;
    font-size: 3rem;
    color: grey;
    background-color: white;
    border: 3px solid grey;
    border-radius: 1rem;
}
button:hover 
{
    background-color: grey;
    color: white;
}
button #prev{
    align-items: flex-start;
}
button #next{
    align-items: flex-end;
}
#slideshow{
    // vertical-align: middle;
    // position: relative;
}
.slide {
    display:hidden;
    width: 60%;
    height: 60%;
    margin:auto;
    // position: absolute;
    // top: 50%;
    // left:50%;
    // -ms-transform: translate(-50%, -50%);
    // transform: translate(-50%, -50%);
}

// .video-container {
//     overflow: hidden;
//     position: relative;
// }

// .video-container::after {
//     padding-top: 56.25%;
//     display: block;
//     content: '';
// }

// .video-container iframe {
//     position: absolute;
//     top: 0;
//     left: 0;
//     width: 100%;
//     height: 100%;
// }
</style>

<script>
export default {
    props:
    {
        activeSlide:
        {
            default: 3
        }
    },
    methods: {
        nextSlide: () => {
            
        },
        prevSlide: () => {
            
        }
    }
}
</script>