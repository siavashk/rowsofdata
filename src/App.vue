<script>
import {Niivue} from '@niivue/niivue'
const nvs = [new Niivue(), new Niivue()]


export default {
    name: 'App',
    props: {},
    data(){
    return {
        sampleList: [
            [
                {
                    url: "/sacralization/imagesTr/la_001_0000.nii.gz",
                    colormap: "gray",
                    visible: true,
                    opacity: 1
                },
                {
                    url: "/sacralization/labelsTr/la_001.nii.gz", 
                    colormap: "red",
                    cal_min: 2,
                    cal_max: 2,
                    visible: true,
                    opacity: 1
                }
            ],
            [
                {
                    url: "/sacralization/imagesTr/la_002_0000.nii.gz",
                    colormap: "gray",
                    visible: true,
                    opacity: 1
                },
                {
                    url: "/sacralization/labelsTr/la_002.nii.gz", 
                    colormap: "red",
                    cal_min: 2,
                    cal_max: 2,
                    visible: true,
                    opacity: 1
                }
            ]
        ]
    }
},
    mounted() {
        for (let i = 0; i < 2; i++) {
            nvs[i].attachTo(`gl${i + 1}`)
            nvs[i].loadVolumes(this.sampleList[i])
        }
    }
}

</script>

<template>
    <canvas id="gl1" height="480" width="640">
    </canvas>
    <canvas id="gl2" height="480" width="640">
    </canvas>
</template>