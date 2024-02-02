<script setup lang="ts">
// components
import VdisplayOption from './components/VdisplayOption.vue'
import HoverContainer from './components/HoverContainer.vue'

// utils
import { ref } from 'vue'

const numberCode = ref('117013')

const services = ref({
    nhentai: true,
    tsumino: false,
    hitomila: false,
    ehentai: false,
    danbooru: false,
    gelbooru: false,
    sankaku: false,
    pixiv: false,
    yandere: false,
    e621: false,
    rule34: false,
    getchu: false,
})
</script>

<template>
    <div class="hero min-h-screen bg-gradient-to-r from-slate-800 to-gray-900">
        <!-- content here -->
        <div class="hero-content flex-col">
            <!-- title -->
            <div>
                <h1
                    class="text-5xl font-bold text-amber-600 underline decoration-amber-300 decoration-dotted"
                >
                    Poneglyph
                </h1>

                <p class="w-64 pt-3 pb-9 text-xs">
                    Turn your magic numbers into clickable links that you can
                    open, or copy to share.
                </p>
            </div>

            <div class="flex flex-row gap-6">
                <!-- left -->
                <div class="space-y-5">
                    <input
                        type="text"
                        placeholder="e.g. 177013"
                        class="input-bordered input w-full max-w-xs rounded-full text-center placeholder-slate-600"
                        v-model="numberCode"
                    />

                    <!-- checkboxes for the services -->
                    <div class="flex flex-col gap-1">
                        <HoverContainer>
                            <label class="label cursor-pointer">
                                <span class="label-text">nHentai</span>
                                <input
                                    type="checkbox"
                                    class="checkbox"
                                    v-model="services.nhentai"
                                    :true-value="true"
                                    :false-value="false"
                                />
                            </label>
                        </HoverContainer>

                        <HoverContainer>
                            <label class="label cursor-pointer">
                                <span class="label-text">Tsumino</span>
                                <input
                                    type="checkbox"
                                    class="checkbox"
                                    v-model="services.tsumino"
                                    :true-value="true"
                                    :false-value="false"
                                />
                            </label>
                        </HoverContainer>

                        <HoverContainer>
                            <label class="label cursor-pointer">
                                <span class="label-text">Hitomi.la</span>
                                <input
                                    type="checkbox"
                                    class="checkbox"
                                    v-model="services.hitomila"
                                    :true-value="true"
                                    :false-value="false"
                                />
                            </label>
                        </HoverContainer>

                        <HoverContainer>
                            <label class="label cursor-pointer">
                                <span class="label-text">e-hentai</span>
                                <input
                                    type="checkbox"
                                    class="checkbox"
                                    v-model="services.ehentai"
                                    :true-value="true"
                                    :false-value="false"
                                />
                            </label>
                        </HoverContainer>

                        <HoverContainer>
                            <label class="label cursor-pointer">
                                <span class="label-text">Danbooru</span>
                                <input
                                    type="checkbox"
                                    class="checkbox"
                                    v-model="services.danbooru"
                                    :true-value="true"
                                    :false-value="false"
                                />
                            </label>
                        </HoverContainer>

                        <HoverContainer>
                            <label class="label cursor-pointer">
                                <span class="label-text">Gelbooru</span>
                                <input
                                    type="checkbox"
                                    class="checkbox"
                                    v-model="services.gelbooru"
                                    :true-value="true"
                                    :false-value="false"
                                />
                            </label>
                        </HoverContainer>

                        <HoverContainer>
                            <label class="label cursor-pointer">
                                <span class="label-text">Sankaku</span>
                                <input
                                    type="checkbox"
                                    class="checkbox"
                                    v-model="services.sankaku"
                                    :true-value="true"
                                    :false-value="false"
                                />
                            </label>
                        </HoverContainer>

                        <HoverContainer>
                            <label class="label cursor-pointer">
                                <span class="label-text">Pixiv</span>
                                <input
                                    type="checkbox"
                                    class="checkbox"
                                    v-model="services.pixiv"
                                    :true-value="true"
                                    :false-value="false"
                                />
                            </label>
                        </HoverContainer>

                        <HoverContainer>
                            <label class="label cursor-pointer">
                                <span class="label-text">Yande.re</span>
                                <input
                                    type="checkbox"
                                    class="checkbox"
                                    v-model="services.yandere"
                                    :true-value="true"
                                    :false-value="false"
                                />
                            </label>
                        </HoverContainer>

                        <HoverContainer>
                            <label class="label cursor-pointer">
                                <span class="label-text">e621</span>
                                <input
                                    type="checkbox"
                                    class="checkbox"
                                    v-model="services.e621"
                                    :true-value="true"
                                    :false-value="false"
                                />
                            </label>
                        </HoverContainer>

                        <HoverContainer>
                            <label class="label cursor-pointer">
                                <span class="label-text">Rule 34</span>
                                <input
                                    type="checkbox"
                                    class="checkbox"
                                    v-model="services.rule34"
                                    :true-value="true"
                                    :false-value="false"
                                />
                            </label>
                        </HoverContainer>

                        <HoverContainer>
                            <label class="label cursor-pointer">
                                <span class="label-text">Getchu</span>
                                <input
                                    type="checkbox"
                                    class="checkbox"
                                    v-model="services.getchu"
                                    :true-value="true"
                                    :false-value="false"
                                />
                            </label>
                        </HoverContainer>
                    </div>
                </div>

                <!-- right -->
                <div class="flex flex-col gap-3">
                    <TransitionGroup>
                        <VdisplayOption
                            link-title="nHentai"
                            :hyper-link="`https://nhentai.net/g/${numberCode}`"
                            v-if="services.nhentai && numberCode"
                        />

                        <VdisplayOption
                            link-title="Tsumino"
                            :hyper-link="`https://www.tsumino.com/entry/${numberCode}`"
                            v-if="services.tsumino && numberCode"
                        />

                        <VdisplayOption
                            link-title="Hitomi.la"
                            :hyper-link="`https://hitomi.la/reader/${numberCode}.html`"
                            v-if="services.hitomila && numberCode"
                        />

                        <VdisplayOption
                            link-title="e-hentai"
                            :hyper-link="`https://e-hentai.org/g/${numberCode}`"
                            v-if="services.ehentai && numberCode"
                        />

                        <VdisplayOption
                            link-title="Danbooru"
                            :hyper-link="`https://danbooru.donmai.us/posts/${numberCode}`"
                            v-if="services.danbooru && numberCode"
                        />

                        <VdisplayOption
                            link-title="Gelbooru"
                            :hyper-link="`https://gelbooru.com/index.php?page=post&s=view&id=${numberCode}`"
                            v-if="services.gelbooru && numberCode"
                        />

                        <VdisplayOption
                            link-title="Sankaku"
                            :hyper-link="`https://chan.sankakucomplex.com/post/show/${numberCode}`"
                            v-if="services.sankaku && numberCode"
                        />

                        <VdisplayOption
                            link-title="Pixiv"
                            :hyper-link="`https://www.pixiv.net/en/artworks/${numberCode}`"
                            v-if="services.pixiv && numberCode"
                        />

                        <VdisplayOption
                            link-title="Yande.re"
                            :hyper-link="`https://yande.re/post/show/${numberCode}`"
                            v-if="services.yandere && numberCode"
                        />

                        <VdisplayOption
                            link-title="e621"
                            :hyper-link="`https://e621.net/post/show/${numberCode}`"
                            v-if="services.e621 && numberCode"
                        />

                        <VdisplayOption
                            link-title="rule34"
                            :hyper-link="`https://rule34.xxx/index.php?page=post&s=view&id=${numberCode}`"
                            v-if="services.rule34 && numberCode"
                        />

                        <VdisplayOption
                            link-title="Getchu"
                            :hyper-link="`http://www.getchu.com/soft.phtml?id=${numberCode}`"
                            v-if="services.getchu && numberCode"
                        />
                    </TransitionGroup>
                </div>
            </div>
        </div>
    </div>

    <footer class="footer footer-center p-3 pt-6 text-base-content">
        <div>
            <a
                class="link text-xs"
                href="https://www.flaticon.com/free-icons/ui"
                title="ui icons"
                target="_blank"
            >
                Ui icons created by Soremba - Flaticon
            </a>
        </div>
    </footer>
</template>

<style scoped>
.v-enter-active,
.v-leave-active {
    transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
    opacity: 0;
}
</style>
