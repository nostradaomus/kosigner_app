<template>
  <main class="flex">

    <!-- Content -->
    <div class="w-full md:w-1/2">

      <div class="min-h-screen h-full flex flex-col justify-center">

        <div class="px-5 sm:px-6 py-8">
          <div class="w-full max-w-md mx-auto">

            <!-- Site branding -->
            <div class="mb-6">
              <!-- Logo -->
              <router-link class="block" to="/">
                <svg width="32" height="32" viewBox="0 0 32 32">
                  <defs>
                    <linearGradient x1="28.538%" y1="20.229%" x2="100%" y2="108.156%" id="logo-a">
                      <stop stop-color="#A5B4FC" stop-opacity="0" offset="0%" />
                      <stop stop-color="#A5B4FC" offset="100%" />
                    </linearGradient>
                    <linearGradient x1="88.638%" y1="29.267%" x2="22.42%" y2="100%" id="logo-b">
                      <stop stop-color="#38BDF8" stop-opacity="0" offset="0%" />
                      <stop stop-color="#38BDF8" offset="100%" />
                    </linearGradient>
                  </defs>
                  <rect fill="#6366F1" width="32" height="32" rx="16" />
                  <path d="M18.277.16C26.035 1.267 32 7.938 32 16c0 8.837-7.163 16-16 16a15.937 15.937 0 01-10.426-3.863L18.277.161z" fill="#4F46E5" />
                  <path d="M7.404 2.503l18.339 26.19A15.93 15.93 0 0116 32C7.163 32 0 24.837 0 16 0 10.327 2.952 5.344 7.404 2.503z" fill="url(#logo-a)" />
                  <path d="M2.223 24.14L29.777 7.86A15.926 15.926 0 0132 16c0 8.837-7.163 16-16 16-5.864 0-10.991-3.154-13.777-7.86z" fill="url(#logo-b)" />
                </svg>
              </router-link>
            </div>

            <h1 class="h2 font-playfair-display text-slate-800 mb-12">Sign in to Tidy</h1>

            <!-- Social login -->
            <div class="space-y-3">
              <button class="btn-sm p-0 text-white bg-rose-500 hover:bg-rose-600 w-full relative flex items-stretch">
                <div class="flex items-center bg-rose-600 mr-4">
                  <svg class="w-4 h-4 fill-current text-rose-100 shrink-0 mx-3" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
                    <path d="M7.9 7v2.4H12c-.2 1-1.2 3-4 3-2.4 0-4.3-2-4.3-4.4 0-2.4 2-4.4 4.3-4.4 1.4 0 2.3.6 2.8 1.1l1.9-1.8C11.5 1.7 9.9 1 8 1 4.1 1 1 4.1 1 8s3.1 7 7 7c4 0 6.7-2.8 6.7-6.8 0-.5 0-.8-.1-1.2H7.9z" />
                  </svg>
                </div>
                <span class="flex-auto text-rose-50 text-sm py-2 pl-14 pr-8 -ml-14">Login with Google</span>
              </button>
            </div>

            <!-- Divider -->
            <div class="flex items-center my-6">
              <div class="border-t border-slate-200 grow mr-3" aria-hidden="true"></div>
              <div class="text-sm text-slate-500 italic">or</div>
              <div class="border-t border-slate-200 grow ml-3" aria-hidden="true"></div>
            </div>

            <!-- Form -->
            <form>
              <div class="space-y-4">
                <div>
                  <label class="block text-sm font-medium mb-1" for="email">Email <span class="text-rose-500">*</span></label>
                  <input id="email" class="form-input py-2 w-full" type="email" required />
                </div>
                <div>
                  <label class="block text-sm font-medium mb-1" for="password">Password <span class="text-rose-500">*</span></label>
                  <input id="password" class="form-input py-2 w-full" type="password" autocomplete="on" required />
                </div>
              </div>
              <div class="mt-6">
                <router-link class="text-blue-600 hover:underline" to="/dashboard">
                  <button @click="" class="btn-sm w-full text-sm text-white bg-blue-600 hover:bg-blue-700 group">
                    Sign In <span class="tracking-normal text-blue-300 group-hover:translate-x-0.5 transition-transform duration-150 ease-in-out ml-1">-&gt;</span>
                  </button>
                </router-link>
              </div>
              <div class="text-center mt-5">
                <router-link class="text-blue-600 hover:underline" to="/reset-password">Forgot your password?</router-link>
              </div>
            </form>

          </div>
        </div>

      </div>

    </div>

    <!-- Right side -->
    <div class="relative hidden md:block md:w-1/2 bg-slate-900" aria-hidden="true">

      <!-- Bg image -->
      <div class="absolute inset-0" data-aos="fade">
        <img class="opacity-10 w-full h-full object-cover" src="../images/sign-in-bg.jpg" width="760" height="900" alt="Background" />
      </div>

      <!-- Quote -->
      <div class="min-h-screen h-full flex flex-col justify-center">
        <div class="px-5 sm:px-6">
          <div class="w-full max-w-lg mx-auto">
            <h2 class="h3 md:text-4xl font-playfair-display text-slate-100 mb-4">The Wealth Inc.</h2>
            <div class="space-y-3">
              <svg class="fill-blue-600" width="20" height="16" viewBox="0 0 20 16">
                <path d="M2.76 16c2.577 0 5.154-3.219 5.154-5.996 0-1.357-.613-2.272-1.748-2.272s-2.27.726-3.283 1.64C3.16 6.439 5.613 3.346 9.571.885L9.233 0C3.466 2.903 0 7.732 0 12.213 0 14.517.828 16 2.76 16Zm10.43 0c2.577 0 5.154-3.219 5.154-5.996 0-1.357-.614-2.272-1.749-2.272-1.135 0-2.27.726-3.282 1.64.276-2.934 2.73-6.027 6.687-8.488L19.663 0c-5.767 2.903-9.234 7.732-9.234 12.213 0 2.304.829 3.787 2.761 3.787Z" />
              </svg>
              <blockquote class="text-slate-400 italic">Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur e xcepteur sint occaecat cupidatat non proident, sunt in culpa qui officia.</blockquote>
            </div>
            <div class="flex items-center mt-4">
              <router-link to="#0">
                <img class="rounded-full shrink-0 mr-3" src="../images/customer-avatar-05.jpg" width="32" height="32" alt="Customer Avatar 05" />
              </router-link>
              <div class="font-medium">
                <span class="text-slate-200">Michael Crob</span>
                <span class="text-slate-600"> · </span>
                <span class="text-slate-500">CEO, The Wealth Inc.</span>
              </div>
            </div>
          </div>
        </div>
      </div>

    </div>

  </main>
</template>

<script>
export default {
  name: 'SignIn',
}
</script>
