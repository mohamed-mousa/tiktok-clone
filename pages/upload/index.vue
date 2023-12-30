<template>
  <UploadLayout>
    <div
      class="w-full mt-[80px] mb-[40px] bg-white shadow-lg rounded-md py-6 md:px-10 px-4"
    >
      <div>
        <div class="text-[23px] font-semibold">Upload video</div>
        <div class="text-gray-400 mt-1">Post a video to your account</div>
      </div>

      <div class="mt-8 md:flex gap-6">
        <label
          v-if="false"
          class="md:mx-0 mx-auto mt-4 mb-6 flex flex-col text-center justify-center w-full max-w-[260px] h-[470px] items-center p-3 border-2 border-dashed border-gray-300 rounded-lg hover:bg-gray-100 cursor-pointer"
        >
          <Icon name="majesticons:cloud-upload" size="40" color="#b3b3b1" />
          <div class="mt-4 text-[17px]">Select video to upload</div>
          <div class="mt-1.5 text-gray-500 text-[13px]">
            Or drag and drop a file
          </div>
          <div class="mt-12 text-gray-400 text-sm">MP4</div>
          <div class="mt-2 text-gray-400 text-[13px]">Up to 30 minutes</div>
          <div class="mt-2 text-gray-400 text-[13px]">Less than 2 GB</div>
          <div
            class="px-2 py-1.5 mt-8 text-white text-[15px] w-[80%] bg-[#f02c56] rounded-sm mx-auto"
          >
            Select file
          </div>
          <input type="file" id="fileInput" ref="file" accept=".mp4" hidden />
        </label>

        <div
          v-else
          class="md:mx-0 mx-auto mt-4 mb-16 md:mb-12 flex items-center justify-center w-full max-w-[260px] h-[540px] p-3 rounded-2xl relative cursor-pointer"
        >
          <div class="bg-black p-3 h-full w-full"></div>
          <img
            src="~/assets/images/mobile-case.png"
            class="absolute z-20 pointer-events-none"
          />
          <img
            src="~/assets/images/tiktok-logo-white.png"
            class="absolute z-20 right-4 bottom-6"
            width="90"
          />
          <video
            :src="url"
            class="rounded-xl absolute z-10 p-[13px] object-cover h-full"
            loop
            muted
            autoplay
          />

          <div
            class="absolute -bottom-12 flex items-center justify-between z-50 rounded-xl border w-full p-2 border-gray-300"
          >
            <div class="flex items-center truncate">
              <Icon
                name="clarity:success-standard-line"
                size="16"
                class="min-w-[16px]"
              />
              <div class="text-[11px] pl-1 truncate text-ellipsis">
                Video name
              </div>
            </div>

            <button class="text-[11px] ml-2 font-semibold">Change</button>
          </div>
        </div>

        <div class="mt-4 mb-6"></div>
      </div>
    </div>
  </UploadLayout>
</template>

<script setup>
import UploadLayout from "~/layouts/UploadLayout.vue";
let url =
  "https://download-video.akamaized.net/v3-1/playback/d673f5b7-4fa6-4eb7-8e33-a9c84ccb1a93/87cf2286?__token__=st=1702374843~exp=1702389243~acl=%2Fv3-1%2Fplayback%2Fd673f5b7-4fa6-4eb7-8e33-a9c84ccb1a93%2F87cf2286%2A~hmac=2cad7ecf7b4b6c91a1e44dd6de95ee3755678baefe397b2ad72d7a7fefa2f486&r=dXMtd2VzdDE%3D";
</script>
