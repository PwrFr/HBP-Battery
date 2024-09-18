<script setup>
import { ArrowRight } from 'lucide-vue-next';

import { ref, onMounted, watch, toRefs, computed } from 'vue';
import { useScroll } from '@vueuse/core'



const currentImage = ref('');
const el = ref < HTMLElement | null > (null)
const { x, y, isScrolling, arrivedState, directions } = useScroll(el, { behavior: 'smooth' })
const { left, right, top, bottom } = toRefs(arrivedState)
const { left: toLeft, right: toRight, top: toTop, bottom: toBottom } = toRefs(directions)

// Format the numbers with toFixed() to make them
// nicer to display
const displayX = computed({
    get() {
        return x.value.toFixed(1)
    },
    set(val) {
        x.value = Number.parseFloat(val)
    },
})
const displayY = computed({
    get() {
        return y.value.toFixed(1)
    },
    set(val) {
        y.value = Number.parseFloat(val)
    },
})

onMounted(() => {
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.intersectionRatio > 0) {
                currentImage.value = entry.target.getAttribute('id')
            }

        });
    })
    document.querySelectorAll('p').forEach((section) => {
        observer.observe(section)
    })
})

const renderComponent = ref(true);

const forceRerender = async () => {
    // Remove MyComponent from the DOM
    renderComponent.value = false;

    // Wait for the change to get flushed to the DOM
    await nextTick();

    // Add the component back in
    renderComponent.value = true;
};

watch(currentImage, () => {
    forceRerender
})
</script>

<template>
    <div class="h-screen w-screen bg-slate-700 bg-fixed bg-center bg-no-repeat bg-cover bg-image relative">
        <!-- Backdrop for the blur effect -->
        <div class="backdrop-blur-[5px] w-full h-full relative">
            <!-- Navbar -->
            <div class="bg-gradient-to-b from-black px-8 pt-4 pb-10 text-white flex justify-between items-center">
                <button class="text-slate-200 hover:text-white duration-200 z-40" v-motion-slide-left>หน้าหลัก</button>
                <div class="font-medium text-lg z-40" v-motion-slide-top>HBP Battery</div>
                <button class="bg-white/25 hover:bg-white/35 duration-200 px-12 py-1.5 rounded-lg"
                    v-motion-slide-right>ติดต่อเรา</button>
            </div>

            <!-- Main Content -->
            <div class="absolute top-1/3 left-[10%] text-white space-y-4">
                <h1 class="text-[48px] font-bold w-[100%] leading-[4rem] " v-motion-slide-visible-left>HBP Battery <br>

                    ผู้เชี่ยวชาญด้านพ่วงแบตเตอรี่ฉุกเฉิน <br>
                    สำหรับรถยนต์เฉพาะรุ่น
                </h1>

                <!-- Call to Action Buttons -->
                <div class="flex space-x-4">
                    <a href="#our-service" v-motion-slide-visible-bottom
                        class="bg-white hover:bg-slate-100 duration-200 text-black py-2 px-6 rounded-md shadow-lg">
                        บริการของเรา
                    </a>
                    <button v-motion-slide-visible-bottom
                        class="bg-yellow-500 hover:bg-yellow-600 duration-200 text-white py-2 px-6 rounded-md shadow-lg">
                        0964962516
                    </button>
                </div>
            </div>
        </div>
    </div>
    <div class=" w-screen grid grid-cols-12 ">

        <div class="col-span-7 p-20">
            <div class="sticky top-20 text-center" v-show="renderComponent" style="text-align: -webkit-center;">

                <img :src="currentImage" class="rounded-xl  w-[90%]" v-motion-slide-visible-left>
            </div>

        </div>
        <div class="col-span-5 bg-neutral-800 text-white px-10 shadow-xl overflow-hidden">
            <h1 class="text-4xl font-bold pt-10" id="our-service" v-motion-slide-visible-right>บริการของเรา</h1>
            <div class="box w-3/4 mt-12 m-8">
                <h1 class="text-3xl font-bold" v-motion-slide-visible-right>บริการเปลี่ยนแบตเตอรี่นอกสถานที่</h1>
                <p class="py-12 text-xl font-light" id="src/assets/images/18417_0.jpg" v-motion-slide-visible-right>
                    หมดกังวลเรื่องแบตเตอรี่หมด!
                    เราพร้อมให้บริการ
                    เปลี่ยนแบตเตอรี่นอกสถานที่ ภายใน
                    20
                    กิโลเมตร
                    เราจะถึงคุณอย่างรวดเร็ว</p>
                <button class="border-b py-1 flex items-center group" v-motion-slide-visible-right>โทรหาเรา
                    <ArrowRight size="20" class="ml-4 group-hover:translate-x-2 duration-200 ease-in-out" />

                </button>
                <!-- <p id="src/assets/images/18422_0.jpg" class="mt-[100dvh]">&nbsp;</p> -->
            </div>


            <div class="box w-3/4 mt-[100dvh] m-8">
                <h1 class="text-3xl font-bold" v-motion-slide-visible-right>พ่วงแบตเตอรี่ฉุกเฉิน</h1>
                <p class="py-12 text-xl font-light" id="src/assets/images/18414_0.jpg" v-motion-slide-visible-right>
                    แบตเตอรี่หมดกระทันหัน? ให้เราช่วย
                    พ่วงแบตเตอรี่
                    และพาคุณกลับสู่เส้นทางอย่างปลอดภัย</p>
                <button class="border-b py-1 flex items-center group" v-motion-slide-visible-right>โทรหาเรา
                    <ArrowRight size="20" class="ml-4 group-hover:translate-x-2 duration-200 ease-in-out" />

                </button>
                <!-- <p id="src/assets/images/18420_0.jpg" class="mt-[100dvh]">&nbsp;</p>

                <p id="src/assets/images/18415_0.jpg" class="my-[100dvh]">&nbsp;</p> -->
            </div>
            <div class="box w-3/4 mt-[100dvh] m-8">
                <h1 class="text-3xl font-bold" v-motion-slide-visible-right>บริการจั๊มแบตเตอรี่นอกสถานที่</h1>
                <p class="py-12 text-xl font-light" id="src/assets/images/18418_0.jpg" v-motion-slide-visible-right>
                    เมื่อคุณกำลังจะออกไปทำงาน
                    รถของคุณสตาร์ทไม่ติดในตอนเช้าตรู่
                    เรียกใช้บริการ
                    จั๊มแบตเตอรี่ เราจะเร่งด่วนไปช่วยคุณในทันที
                </p>
                <button class="border-b py-1 flex items-center group" v-motion-slide-visible-right>โทรหาเรา
                    <ArrowRight size="20" class="ml-4 group-hover:translate-x-2 duration-200 ease-in-out" />

                </button>
            </div>
            <div class="box w-3/4 mt-[100dvh] m-8">
                <!-- <p id="src/assets/images/a1.jpg" class="my-[100dvh]">&nbsp;</p> -->

                <p class="py-12 text-xl font-light" id="src/assets/images/a5.jpg" v-motion-slide-visible-right>ที่ HBP
                    Battery
                    เราเลือกใช้แบตเตอรี่คุณภาพสูงจากแบรนด์ชั้นนำ
                    แบรนด์เหล่านี้เป็นที่ยอมรับในตลาดด้วยประสิทธิภาพที่ยอดเยี่ยม ความทนทาน และมาตรฐานการผลิตระดับสากล
                    คุณจึงมั่นใจได้ว่ารถของคุณจะได้รับการดูแลด้วยแบตเตอรี่ที่ดี
                    ที่สุด พร้อมรับประกันการใช้งานที่ยาวนานและความปลอดภัยสูงสุด
                </p>
                <button class="border-b py-1 flex items-center group" v-motion-slide-visible-right>โทรหาเรา
                    <ArrowRight size="20" class="ml-4 group-hover:translate-x-2 duration-200 ease-in-out" />

                </button>
                <!-- <p id="src/assets/images/a6.jpg" class="mt-[100dvh]">&nbsp;</p> -->

            </div>
            <div class="box w-3/4 mt-[100dvh] mb-[20dvh] m-8">
                <p class="py-12 text-xl font-light" id="src/assets/images/18474.jpg" v-motion-slide-visible-right>HBP
                    Battery
                    ได้รับการจดทะเบียนพาณิชย์อย่างถูกต้องตามกฎหมาย
                    เรามุ่งมั่นในการดำเนินธุรกิจด้วยความโปร่งใสและมีมาตรฐาน
                    ลูกค้าจึงมั่นใจได้ในคุณภาพของสินค้าและบริการจากเรา ด้วยการรับรองที่ถูกต้องจากหน่วยงานราชการ
                    คุณสามารถวางใจได้ว่า HBP Battery เป็นร้านที่มีความน่าเชื่อถือและให้บริการที่ซื่อสัตย์ จริงใจ
                </p>
                <button class="border-b py-1 flex items-center group" v-motion-slide-visible-right>ข้อมูลทะเบียนพาณิชย์
                    <ArrowRight size="20" class="ml-4 group-hover:translate-x-2 duration-200 ease-in-out" />

                </button>
            </div>


        </div>


    </div>
</template>

<style>
.bg-image {
    background-image: url('./assets/images/18428_0.jpg');
    background-size: cover;

}
</style>
