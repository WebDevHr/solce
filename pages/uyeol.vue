<template>
    <div class=" bg-[url('/pictures/sign-image.webp')]">
        <div class="flex justify-center pb-20 pt-32 bg-gradient-to-t from-[#06021f] to-transparent">
            <div
                class="flex min-h-full flex-1 flex-col justify-center px-6 lg:px-8 border rounded-lg max-w-[400px] bg-white py-5">
                <div class="sm:mx-auto sm:w-full sm:max-w-sm">
                    <h2 class="my-5 text-center text-2xl font-bold leading-9 tracking-tight text-gray-900">Hesap
                        Oluştur
                    </h2>
                </div>

                <div class="mt-5 sm:mx-auto sm:w-full sm:max-w-sm">
                    <form class="space-y-3" action="#" method="POST">
                        <div>
                            <label for="email" class="block text-sm font-medium leading-6 text-gray-900">Ad</label>
                            <div class="mt-2">
                                <input id="name" name="name" type="text" autocomplete="name" required="true"
                                    placeholder="Adınız girin ..."
                                    class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-sky-600 sm:text-sm sm:leading-6" />
                            </div>
                        </div>
                        <div>
                            <label for="email" class="block text-sm font-medium leading-6 text-gray-900">Soyad</label>
                            <div class="mt-2">
                                <input id="familyName" name="familyName" type="text" autocomplete="familyName"
                                    required="true" placeholder="Soyadınız girin ..."
                                    class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-sky-600 sm:text-sm sm:leading-6" />
                            </div>
                        </div>
                        <div>
                            <label for="email" class="block text-sm font-medium leading-6 text-gray-900">E-Posta
                                Adresi</label>
                            <div class="mt-2">
                                <input id="email" name="email" type="email" autocomplete="email" required="true"
                                    placeholder="E-Postanızı giriniz ..."
                                    class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-sky-600 sm:text-sm sm:leading-6" />
                            </div>
                        </div>

                        <div>
                            <div class="flex items-center justify-between">
                                <label for="password"
                                    class="block text-sm font-medium leading-6 text-gray-900">Şifre</label>
                            </div>
                            <div class="mt-2">
                                <input id="password" name="password" type="password" autocomplete="current-password"
                                    required="true" placeholder="Şifrenizi giriniz ... "
                                    class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-sky-600 sm:text-sm sm:leading-6" />
                            </div>
                        </div>

                        <div class="pt-5">
                            <button type="submit"
                                class="flex w-full justify-center rounded-md bg-sky-600 px-3 py-2.5 text-sm font-semibold leading-6 text-white shadow-sm hover:bg-sky-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-sky-600">Üye
                                Ol</button>
                        </div>
                    </form>

                    <p class="mt-5 text-center text-sm text-gray-500">
                        Hesabınız Var Mı?
                        {{ ' ' }}
                        <nuxt-link to="/giris" class="font-semibold leading-6 text-sky-600 hover:text-sky-500">Giriş
                            Yap</nuxt-link>
                    </p>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
input {
    padding: 10px;
}
</style>
