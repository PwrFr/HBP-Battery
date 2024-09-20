<script setup>

import { CarFront, PlugZap, ArrowRight, Cable, PhoneOutgoing, SquareArrowOutUpRight } from 'lucide-vue-next';

import { ref, onMounted, watch, toRefs, computed } from 'vue';

import img1 from './assets/images/18414_0.jpg';
import img2 from './assets/images/18423.jpg';
import img3 from './assets/images/18415_0.jpg';
import img4 from './assets/images/18417_0.jpg';
import img5 from './assets/images/18418_0.jpg';
import img6 from './assets/images/18422_0.jpg';
import img7 from './assets/images/18421_0.jpg';
import img8 from './assets/images/18427_0.jpg';

const imageList = [
    img1, img2, img3, img4, img5, img6, img7, img8
]

const ourService = ref()

const scrollToView = () => {
    ourService.value.scrollIntoView()
}

const handleClick = () => {
    const userAgent = navigator.userAgent.toLowerCase();

    if (userAgent.includes('iphone') || userAgent.includes('ipad')) {
        // Open the phone app on iPhone or iPad
        window.location.href = 'tel:0964962516';
    } else if (userAgent.includes('android')) {
        // Open the phone app on Android
        window.location.href = 'tel:0964962516';
    } else if (userAgent.includes('mac')) {
        // Open Facetime on Mac
        window.location.href = 'facetime:0964962516';
    } else {
        // Fallback URL for other platforms
        window.location.href = 'https://example.com'; // Replace with a fallback URL
    }
};
</script>

<template>
    <!-- bg-phone -->
    <div
        class="h-screen w-screen bg-slate-700 bg-fixed bg-center bg-cover bg-no-repeat bg-image relative sm:block hidden">

        <div class="backdrop-blur-[5px] w-full h-full relative ">

            <div
                class="flex bg-gradient-to-b from-black px-8 pt-4 pb-10 text-white  sm:justify-between justify-center items-center">
                <button class="sm:block hidden text-slate-200 hover:text-white duration-200 z-40"
                    v-motion-slide-left>หน้าหลัก</button>
                <div class="font-medium text-lg z-40" v-motion-slide-top>HBP Battery</div>
                <button class="sm:block hidden bg-white/25 hover:bg-white/35 duration-200 px-12 py-1.5 rounded-lg"
                    v-motion-slide-right>ติดต่อเรา</button>
            </div>


            <div
                class="absolute sm:top-1/3 top-[30%] sm:left-[10%] left-0 text-white space-y-4 w-screen sm:text-left text-center ">
                <h1 class="sm:text-[48px] text-4xl font-bold sm:leading-[4rem] leading-[3rem]"
                    v-motion-slide-visible-once-left>
                    HBP
                    Battery <br>
                    <span class="sm:text-[48px] text-2xl">
                        ผู้เชี่ยวชาญด้านแบตเตอรี่ <br> เปลี่ยน พ่วงแบตเตอรี่ฉุกเฉิน <br>
                        สำหรับรถยนต์เฉพาะรุ่น
                    </span>
                </h1>


                <div class="flex space-x-4 sm:justify-start justify-center">
                    <button @click="scrollToView" v-motion-slide-visible-once-bottom
                        class="bg-white hover:bg-slate-100 duration-200 text-black py-2 px-6 rounded-md shadow-lg">
                        บริการของเรา
                    </button>
                    <button v-motion-slide-visible-once-bottom @click="handleClick"
                        class="bg-yellow-500 hover:bg-yellow-600 duration-200 text-white py-2 px-6 rounded-md shadow-lg flex items-center">
                        <PhoneOutgoing size="18" class="mr-2" /> 0964962516
                    </button>
                </div>
            </div>
        </div>
    </div>

    <div class="h-[100dvh] w-[100dvw] bg-slate-700 bg-no-repeat bg-phone sm:hidden block relative">

        <div class="backdrop-blur-[2px] w-full h-full relative ">

            <div
                class="flex bg-gradient-to-b from-black px-8 pt-4 pb-10 text-white  sm:justify-between justify-center items-center">
                <button class="sm:block hidden text-slate-200 hover:text-white duration-200 z-40"
                    v-motion-slide-left>หน้าหลัก</button>
                <div class="font-medium text-lg z-40" v-motion-slide-top>HBP Battery</div>
                <button class="sm:block hidden bg-white/25 hover:bg-white/35 duration-200 px-12 py-1.5 rounded-lg"
                    v-motion-slide-right>ติดต่อเรา</button>
            </div>


            <div
                class="absolute sm:top-1/3 top-[30%] sm:left-[10%] left-0 text-white space-y-4 w-screen sm:text-left text-center ">
                <h1 class="sm:text-[48px] text-4xl font-bold sm:leading-[4rem] leading-[3rem]"
                    v-motion-slide-visible-once-left>
                    HBP
                    Battery <br>
                    <span class="sm:text-[48px] text-2xl">
                        ผู้เชี่ยวชาญด้านแบตเตอรี่ <br> เปลี่ยน พ่วงแบตเตอรี่ฉุกเฉิน <br>
                        สำหรับรถยนต์เฉพาะรุ่น
                    </span>
                </h1>


                <div class="flex space-x-4 sm:justify-start justify-center">
                    <button @click="scrollToView" v-motion-slide-visible-once-bottom
                        class="bg-white hover:bg-slate-100 duration-200 text-black py-2 px-6 rounded-md shadow-lg">
                        บริการของเรา
                    </button>
                    <button v-motion-slide-visible-once-bottom @click="handleClick"
                        class="bg-yellow-500 hover:bg-yellow-600 duration-200 text-white py-2 px-6 rounded-md shadow-lg flex items-center">
                        <PhoneOutgoing size="18" class="mr-2" /> 0964962516
                    </button>
                </div>
            </div>
        </div>
    </div>

    <div class="py-32 bg-white text-black" ref="ourService">
        <h1 class="text-4xl font-bold  text-center" v-motion-slide-visible-once-bottom>
            บริการของเรา
        </h1>
        <div class="container mx-auto grid md:grid-cols-3 grid-cols-1 gap-8 my-20 sm:px-0 px-10">
            <div class="text-center">
                <div class="flex justify-center" v-motion-slide-visible-once-bottom>
                    <CarFront size="100" />
                </div>
                <h1 class="text-3xl font-bold pt-8 pb-4" v-motion-slide-visible-once-bottom>
                    บริการเปลี่ยนแบตเตอรี่นอกสถานที่
                </h1>
                <p class=" text-xl font-light " id="src/assets/images/18417_0.jpg" v-motion-slide-visible-once-bottom>
                    หมดกังวลเรื่องแบตเตอรี่หมด!
                    เราพร้อมให้บริการ
                    เปลี่ยนแบตเตอรี่นอกสถานที่ ภายใน
                    20
                    กิโลเมตร
                    เราจะถึงคุณอย่างรวดเร็ว</p>
            </div>
            <div class="text-center">
                <div class="flex justify-center" v-motion-slide-visible-once-bottom>
                    <Cable size="100" />
                </div>
                <h1 class="text-3xl font-bold pt-8 pb-4" v-motion-slide-visible-once-bottom>พ่วงแบตเตอรี่ฉุกเฉิน</h1>
                <p class="text-xl font-light" id="src/assets/images/18414_0.jpg" v-motion-slide-visible-once-bottom>
                    แบตเตอรี่หมดกระทันหัน? ให้เราช่วย
                    พ่วงแบตเตอรี่
                    และพาคุณกลับสู่เส้นทางอย่างปลอดภัย</p>

            </div>
            <div class="text-center">
                <div class="flex justify-center" v-motion-slide-visible-once-bottom>
                    <PlugZap size="100" />
                </div>
                <h1 class="text-3xl font-bold pt-8 pb-4" v-motion-slide-visible-once-bottom>
                    บริการจั๊มแบตเตอรี่นอกสถานที่
                </h1>
                <p class=" text-xl font-light" id="src/assets/images/18418_0.jpg" v-motion-slide-visible-once-bottom>
                    เมื่อคุณกำลังจะออกไปทำงาน
                    รถของคุณสตาร์ทไม่ติดในตอนเช้าตรู่
                    เรียกใช้บริการ
                    จั๊มแบตเตอรี่ เราจะเร่งด่วนไปช่วยคุณในทันที
                </p>


            </div>
        </div>
        <div class="flex justify-center">
            <button class="border-black border-b-4 py-1 flex items-center group text-2xl" @click="handleClick"
                v-motion-slide-visible-once-left>โทรหาเรา
                <ArrowRight size="28" class="ml-44 group-hover:translate-x-2 duration-200 ease-in-out" />

            </button>

        </div>
    </div>

    <div class="grid md:grid-cols-4 grid-cols-2">

        <!-- <div v-for="img in imageList" class="bg-fixed w-full md:h-[25dvw] h-[50dvw]"
            :style="`background:url(${img}) center center / cover no-repeat; `" /> -->
        <img v-for="img in imageList" :src="img" class="aspect-square object-cover	" />
    </div>
    <div class="py-32">
        <h1 class="text-4xl font-bold  text-center" v-motion-slide-visible-once-bottom>
            มั่นใจได้ถึงคุณภาพ
        </h1>
        <div class="mx-auto container grid md:grid-cols-2 grid-cols-1 lg:gap-8 sm:gap-20 my-20 ">
            <div class="relative flex justify-center h-[344px] sm:scale-100 scale-75">
                <img src="./assets/images/a1.jpg" class="w-44 h-44 absolute mr-60" v-motion-slide-visible-once-bottom
                    :duration="600" alt="">
                <img src="./assets/images/a5.jpg" class="w-44 h-44 absolute mt-40" alt=""
                    v-motion-slide-visible-once-bottom :delay="200" :duration="600">
                <img src="./assets/images/a6.jpg" class="w-44 h-44 absolute ml-72 mt-10" alt=""
                    v-motion-slide-visible-once-bottom :delay="100" :duration="600">

            </div>
            <div v-motion-slide-visible-once-bottom
                class="leading-9 text-xl justify-end text-center flex items-center md:text-left md:pr-16 md:pl-0 lg:pr-40 lg:pl-0 px-10">
                ที่ HBP Battery
                เราเลือกใช้แบตเตอรี่คุณภาพสูงจากแบรนด์ชั้นนำ
                แบรนด์เหล่านี้เป็นที่ยอมรับในตลาดด้วยประสิทธิภาพที่ยอดเยี่ยม ความทนทาน และมาตรฐานการผลิตระดับสากล
                คุณจึงมั่นใจได้ว่ารถของคุณจะได้รับการดูแลด้วยแบตเตอรี่ที่ดี
                ที่สุด พร้อมรับประกันการใช้งานที่ยาวนานและความปลอดภัยสูงสุด</div>
        </div>
    </div>

    <div class="py-32 bg-white text-black">
        <h1 class="text-4xl font-bold  text-center" v-motion-slide-visible-once-bottom>
            การันตีความน่าเชื่อถือ
        </h1>
        <div class="mx-auto container sm:grid md:grid-cols-2 grid-cols-1 gap-16 my-20 flex flex-col-reverse">
            <div class="grid sm:place-items-end place-items-center ">
                <div v-motion-slide-visible-once-bottom
                    class="leading-9 text-xl justify-end text-center flex items-center md:text-right md:pl-16 md:pr-0 lg:pl-40 lg:pr-0 px-10">
                    HBP
                    Battery
                    ได้รับการจดทะเบียนพาณิชย์อย่างถูกต้องตามกฎหมาย
                    เรามุ่งมั่นในการดำเนินธุรกิจด้วยความโปร่งใสและมีมาตรฐาน
                    ลูกค้าจึงมั่นใจได้ในคุณภาพของสินค้าและบริการจากเรา ด้วยการรับรองที่ถูกต้องจากหน่วยงานราชการ
                    คุณสามารถวางใจได้ว่า HBP Battery เป็นร้านที่มีความน่าเชื่อถือและให้บริการที่ซื่อสัตย์ จริงใจ

                </div>
                <a href="https://dbdregcom.dbd.go.th/regc-app/public/rcp010700.xhtml?qr=e70799b8-94b6-4736-b962-2c9f97043337"
                    target="_blank"
                    class="border-black border-b-4 py-1 flex items-center group text-2xl cursor-pointer mt-10"
                    v-motion-slide-visible-once-left>ข้อมูลทะเบียนพาณิชย์
                    <SquareArrowOutUpRight size="28" class="ml-20 group-hover:translate-x-2 duration-200 ease-in-out" />

                </a>
            </div>
            <div class="relative flex md:justify-start justify-center " v-motion-slide-visible-once-bottom>
                <img src="./assets/images/18474.jpg" class="lg:w-1/2 w-[75%]" alt="">


            </div>
        </div>

    </div>

    <div class="pb-14">

        <div class="mx-auto container grid sm:grid-cols-3 grid-cols-1 mt-16 sm:px-0 px-10 sm:text-left text-center">
            <!-- <div v-motion-slide-visible-once-bottom
                class="leading-9 text-xl justify-end text-center flex items-center md:text-right md:pl-16 md:pr-0 lg:pl-40 lg:pr-0 px-10">
                HBP
                Battery
                ได้รับการจดทะเบียนพาณิชย์อย่างถูกต้องตามกฎหมาย
                เรามุ่งมั่นในการดำเนินธุรกิจด้วยความโปร่งใสและมีมาตรฐาน
                ลูกค้าจึงมั่นใจได้ในคุณภาพของสินค้าและบริการจากเรา ด้วยการรับรองที่ถูกต้องจากหน่วยงานราชการ
                คุณสามารถวางใจได้ว่า HBP Battery เป็นร้านที่มีความน่าเชื่อถือและให้บริการที่ซื่อสัตย์ จริงใจ
            </div> -->
            <div class="col-span-1 grid gap-8 ">
                <h1 class="mx-auto container text-4xl font-bold sm:text-left text-center "
                    v-motion-slide-visible-once-bottom>
                    <span class="text-2xl">Contact</span><br> HBP Battery
                </h1>
                <div>
                    <button v-motion-slide-visible-once-bottom @click="handleClick"
                        class="bg-yellow-500 hover:bg-yellow-600 duration-200 text-white py-2 px-6 rounded-md shadow-lg">
                        โทร 0964962516
                    </button>

                </div>
                <!-- <span class="my-10"> -->
                OR

                <!-- </span> -->
                <div class="relative flex sm:justify-start justify-center" v-motion-slide-visible-once-bottom>
                    <img src="./assets/images/18633.jpg" class="sm:w-1/2 w-full h-full" alt="">


                </div>
            </div>
            <div class="col-span-2 flex flex-col">
                <h1 class="mx-auto container text-4xl font-bold sm:text-left text-center my-10"
                    v-motion-slide-visible-once-bottom>
                    ที่ตั้งสำนักงาน

                </h1>
                <iframe
                    src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3875.27796641774!2d100.72549997588037!3d13.762103686630834!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x311d66a36a9d3509%3A0x3971dc4d75d00613!2zMTAxIOC4i-C4reC4oiDguYDguITguKvguLDguKPguYjguKHguYDguIHguKXguYnguLIgS2h3YWVuZyBLaGxvbmcgU29uZyBUb24gTnVuLCBLaGV0IExhdCBLcmFiYW5nLCBLcnVuZyBUaGVwIE1haGEgTmFraG9uIDEwNTIw!5e0!3m2!1sen!2sth!4v1726853845384!5m2!1sen!2sth"
                    width="100%" height="100%" style="border:0;" allowfullscreen="" loading="lazy"
                    referrerpolicy="no-referrer-when-downgrade"></iframe>
            </div>

        </div>

    </div>

    <!-- <div class="p-4 h-screen">
        <h1 class="text-3xl font-bold" v-motion-slide-visible-once-right>พ่วงแบตเตอรี่ฉุกเฉิน</h1>
        <p class="py-12 text-xl font-light" id="src/assets/images/18414_0.jpg" v-motion-slide-visible-once-right>
            แบตเตอรี่หมดกระทันหัน? ให้เราช่วย
            พ่วงแบตเตอรี่
            และพาคุณกลับสู่เส้นทางอย่างปลอดภัย</p>
        <button class="border-b py-1 flex items-center group" v-motion-slide-visible-once-right>โทรหาเรา
            <ArrowRight size="20" class="ml-4 group-hover:translate-x-2 duration-200 ease-in-out" />

        </button>
     
    </div>
    <div class="p-4 h-screen">
        <h1 class="text-3xl font-bold" v-motion-slide-visible-once-right>บริการจั๊มแบตเตอรี่นอกสถานที่</h1>
        <p class="py-12 text-xl font-light" id="src/assets/images/18418_0.jpg" v-motion-slide-visible-once-right>
            เมื่อคุณกำลังจะออกไปทำงาน
            รถของคุณสตาร์ทไม่ติดในตอนเช้าตรู่
            เรียกใช้บริการ
            จั๊มแบตเตอรี่ เราจะเร่งด่วนไปช่วยคุณในทันที
        </p>
        <button class="border-b py-1 flex items-center group" v-motion-slide-visible-once-right>โทรหาเรา
            <ArrowRight size="20" class="ml-4 group-hover:translate-x-2 duration-200 ease-in-out" />

        </button>
    </div>
    <div class="p-4 h-screen">

        <p class="py-12 text-xl font-light" id="src/assets/images/a5.jpg" v-motion-slide-visible-once-right>
            ที่ HBP            Battery
            เราเลือกใช้แบตเตอรี่คุณภาพสูงจากแบรนด์ชั้นนำ
            แบรนด์เหล่านี้เป็นที่ยอมรับในตลาดด้วยประสิทธิภาพที่ยอดเยี่ยม ความทนทาน และมาตรฐานการผลิตระดับสากล
            คุณจึงมั่นใจได้ว่ารถของคุณจะได้รับการดูแลด้วยแบตเตอรี่ที่ดี
            ที่สุด พร้อมรับประกันการใช้งานที่ยาวนานและความปลอดภัยสูงสุด
        </p>
        <button class="border-b py-1 flex items-center group" v-motion-slide-visible-once-right>โทรหาเรา
            <ArrowRight size="20" class="ml-4 group-hover:translate-x-2 duration-200 ease-in-out" />

        </button>

    </div>
    <div class="p-4 h-screen">
        <p class="py-12 text-xl font-light" id="src/assets/images/18474.jpg" v-motion-slide-visible-once-right>HBP
            Battery
            ได้รับการจดทะเบียนพาณิชย์อย่างถูกต้องตามกฎหมาย
            เรามุ่งมั่นในการดำเนินธุรกิจด้วยความโปร่งใสและมีมาตรฐาน
            ลูกค้าจึงมั่นใจได้ในคุณภาพของสินค้าและบริการจากเรา ด้วยการรับรองที่ถูกต้องจากหน่วยงานราชการ
            คุณสามารถวางใจได้ว่า HBP Battery เป็นร้านที่มีความน่าเชื่อถือและให้บริการที่ซื่อสัตย์ จริงใจ
        </p>
        <button class="border-b py-1 flex items-center group" v-motion-slide-visible-once-right>ข้อมูลทะเบียนพาณิชย์
            <ArrowRight size="20" class="ml-4 group-hover:translate-x-2 duration-200 ease-in-out" />

        </button>
    </div> -->


    <!-- </div> -->


    <!-- </div> -->
</template>

<style>
.bg-image {
    background-image: url('./assets/images/18428_0.jpg');
}

.bg-phone {
    background-image: url('./assets/images/18413_0.jpg');

}
</style>
