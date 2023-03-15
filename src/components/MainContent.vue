<template>
  <main class="md:px-4 md:pt-4 md:pb-10 max-w-7xl m-auto pt-8">
    <div class="flex justify-between md:mb-6 items-center mb-6">
      <h1 class="md:text-3xl text-xl pl-4 md:pl-0 font-bold leading-9">Crypto Price in Rupiah Today</h1>
      <div class="relative">
        <div class="md:block hidden">
          <div class="w-96 py-2 px-4 rounded-lg flex cursor-pointer bg-gray-200">
            <div class="block align-middle">🔍</div>
            <div class="ml-4 flex-shrink flex-grow basis-0">
              <div class="text-sm w-full text-slate-400">Look for assets in Doors...</div>
            </div>
          </div>
        </div>
        <div class="md:hidden block">
          <div class="cursor-pointer mx-4">🔍</div>
        </div>
      </div>
    </div>
    <!-- filter -->
    <div class="md:mb-6 mb-4">
      <div class="flex justify-start md:pl-0 overflow-auto">
        <a href="#" class="mr-2">
          <div class="p-2 rounded-lg flex items-center bg-blue-200">
            <div class="mr-2 w-6 h-6">
              <div class="w-full h-full">✨</div>
            </div>
            <div class="text-xs text-blue-500 font-semibold whitespace-nowrap">Terbaru</div>
          </div>
        </a>
        <a href="#" class="mr-2">
          <div class="p-2 rounded-lg flex items-center bg-blue-200">
            <div class="mr-2 w-6 h-6">
              <div class="w-full h-full">🏛️</div>
            </div>
            <div class="text-xs text-blue-500 font-semibold whitespace-nowrap">DeFi</div>
          </div>
        </a>
        <a href="#" class="mr-2">
          <div class="p-2 rounded-lg flex items-center bg-blue-200">
            <div class="mr-2 w-6 h-6">
              <div class="w-full h-full">🎮</div>
            </div>
            <div class="text-xs text-blue-500 font-semibold whitespace-nowrap">NFTs/Gaming</div>
          </div>
        </a>
        <a href="#" class="mr-2">
          <div class="p-2 rounded-lg flex items-center bg-blue-200">
            <div class="mr-2 w-6 h-6">
              <div class="w-full h-full">📈</div>
            </div>
            <div class="text-xs text-blue-500 font-semibold whitespace-nowrap">CEX</div>
          </div>
        </a>
        <a href="#" class="mr-2">
          <div class="p-2 rounded-lg flex items-center bg-blue-200">
            <div class="mr-2 w-6 h-6">
              <div class="w-full h-full">↔️</div>
            </div>
            <div class="text-xs text-blue-500 font-semibold whitespace-nowrap">DEX</div>
          </div>
        </a>
        <a href="#" class="mr-2">
          <div class="p-2 rounded-lg flex items-center bg-blue-200">
            <div class="mr-2 w-6 h-6">
              <div class="w-full h-full">🔀</div>
            </div>
            <div class="text-xs text-blue-500 font-semibold whitespace-nowrap">Layer-1</div>
          </div>
        </a>
        <a href="#" class="mr-2">
          <div class="p-2 rounded-lg flex items-center bg-blue-200">
            <div class="mr-2 w-6 h-6">
              <div class="w-full h-full">🗂️</div>
            </div>
            <div class="text-xs text-blue-500 font-semibold whitespace-nowrap">Infrastructure</div>
          </div>
        </a>
        <a href="#" class="mr-2">
          <div class="p-2 rounded-lg flex items-center bg-blue-200">
            <div class="mr-2 w-6 h-6">
              <div class="w-full h-full">💰</div>
            </div>
            <div class="text-xs text-blue-500 font-semibold whitespace-nowrap">Lending</div>
          </div>
        </a>
        <a href="#" class="mr-2">
          <div class="p-2 rounded-lg flex items-center bg-blue-200">
            <div class="mr-2 w-6 h-6">
              <div class="w-full h-full">🔀</div>
            </div>
            <div class="text-xs text-blue-500 font-semibold whitespace-nowrap">Layer-2</div>
          </div>
        </a>
        <a href="#" class="mr-2">
          <div class="p-2 rounded-lg flex items-center bg-blue-200">
            <div class="mr-2 w-6 h-6">
              <div class="w-full h-full">⚖️</div>
            </div>
            <div class="text-xs text-blue-500 font-semibold whitespace-nowrap">Stable Ecosystem</div>
          </div>
        </a>
      </div>
    </div>
    <!-- Price Table view port > 768px -->
    <div class="border rounded-lg md:block hidden">
      <table class="table-auto w-full divide-y divide-gray-200 overflow-x-auto border-separate indent-0">
        <thead>
          <tr class="text-left text-slate-400">
            <th class="py-5 pr-5 pl-[75px]"><p>CRYPTO</p></th>
            <th class="p-5"><p>PRICE</p></th>
            <th class="p-5 text-center"><p>24 HOURS</p></th>
            <th class="p-5 text-center"><p>1 WEEK</p></th>
            <th class="p-5 text-center"><p>1 MO</p></th>
            <th class="p-5 text-center"><p>1 YR</p></th>
          </tr>
        </thead>
        <tbody class="">
          <tr v-for="(item, index) in state.items" :key="index">
            <td class="p-5">
              <a href="#">
                <div class="flex items-center">
                  <div class="w-8 h-8" :class="`text-[${item.color}]`"><img :src="item.logo" :alt="item.name" class="w-full h-full fill-current" /></div>
                  <div class="flex flex-wrap flex-grow flex-shrink basis-0">
                    <p class="ml-4 flex flex-grow flex-shrink basis-0 font-semibold text-base">{{ item.name }}</p>
                    <p class="mx-6 w-14 text-slate-500">{{ item.symbol }}</p>
                  </div>
                </div>
              </a>
            </td>
            <td class="p-5 text-base font-semibold">IDR {{ item.latestPrice?.latestPrice }}</td>
            <td class="p-2 w-32 text-base font-semibold">
              <div class="flex items-center justify-center" :class="{ 'text-green-500': item.latestPrice?.day >= 0, 'text-red-500': item.latestPrice?.day < 0 }">
                <div class="border-b-green-600 border-t-transparent border-x-transparent border-solid border-t-0 border-b-8 border-x-[6px] h-0 w-0 mr-[5px] self-center" v-if="item.latestPrice?.day >= 0"></div>
                <div class="border-t-red-600 border-b-transparent border-x-transparent border-solid border-t-8 border-b-0 border-x-[6px] h-0 w-0 mr-[5px] self-center" v-else="item.latestPrice?.day < 0"></div>
                <p>{{ item.latestPrice?.day }} %</p>
              </div>
            </td>
            <td class="p-2 w-32 text-base font-semibold">
              <div class="flex items-center justify-center" :class="{ 'text-green-500': item.latestPrice?.week >= 0, 'text-red-500': item.latestPrice?.week < 0 }">
                <div class="border-b-green-600 border-t-transparent border-x-transparent border-solid border-t-0 border-b-8 border-x-[6px] h-0 w-0 mr-[5px] self-center" v-if="item.latestPrice?.week >= 0"></div>
                <div class="border-t-red-600 border-b-transparent border-x-transparent border-solid border-t-8 border-b-0 border-x-[6px] h-0 w-0 mr-[5px] self-center" v-else="item.latestPrice?.week < 0"></div>
                <p>{{ item.latestPrice?.week }}%</p>
              </div>
            </td>
            <td class="p-2 w-32 text-base font-semibold">
              <div class="flex items-center justify-center" :class="{ 'text-green-500': item.latestPrice?.month >= 0, 'text-red-500': item.latestPrice?.month < 0 }">
                <div class="border-b-green-600 border-t-transparent border-x-transparent border-solid border-t-0 border-b-8 border-x-[6px] h-0 w-0 mr-[5px] self-center" v-if="item.latestPrice?.month >= 0"></div>
                <div class="border-t-red-600 border-b-transparent border-x-transparent border-solid border-t-8 border-b-0 border-x-[6px] h-0 w-0 mr-[5px] self-center" v-else="item.latestPrice?.month < 0"></div>
                <p>{{ item.latestPrice?.month }}%</p>
              </div>
            </td>
            <td class="p-2 w-32 text-base font-semibold">
              <div class="flex items-center justify-center" :class="{ 'text-green-500': item.latestPrice?.year >= 0, 'text-red-500': item.latestPrice?.year < 0 }">
                <div class="border-b-green-600 border-t-transparent border-x-transparent border-solid border-t-0 border-b-8 border-x-[6px] h-0 w-0 mr-[5px] self-center" v-if="item.latestPrice?.year >= 0"></div>
                <div class="border-t-red-600 border-b-transparent border-x-transparent border-solid border-t-8 border-b-0 border-x-[6px] h-0 w-0 mr-[5px] self-center" v-else="item.latestPrice?.year < 0"></div>
                <p>{{ item.latestPrice?.year }}%</p>
              </div>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
    <!-- Price Table view Port < 76px -->
    <div class="md:hidden block">
      <div>
        <div class="border border-t flex p-4 items-center justify-between">
          <div class="text-xs font-semibold flex-grow flex-shrink basis-0">CRYPTO</div>
          <div class="pl-4">
            <select name="time-frame" id="time-frame" class="rounded-md font-semibold text-xs p-1 border">
              <option value="24 HOURS">24 HOURS</option>
              <option value="1 WEEK">1 WEEEK</option>
              <option value="1 MONTH">1 MONTH</option>
              <option value="1 YEAR">1 YEAR</option>
            </select>
          </div>
        </div>
        <div>
          <div v-for="(item, index) in state.items" :key="index">
            <a href="#">
              <div class="p-4 flex items-center border-t">
                <div class="h-8 w-8">
                  <img :src="item.logo" :alt="item.name" class="w-full h-full" />
                </div>
                <div class="pl-6 flex flex-shrink flex-grow basis-0">
                  <div class="flex-shrink flex-grow basis-0">
                    <div class="text-base font-semibold">{{ item.name }}</div>
                    <div class="text-sm">{{ item.symbol }}</div>
                  </div>
                  <div>
                    <div class="text-base font-semibold text-right">IDR {{ item.latestPrice?.latestPrice }}</div>
                    <div class="flex justify-end text-sm">
                      <div class="flex text-right font-semibold align-middle justify-center">
                        <div class="border-b-green-600 border-t-transparent border-x-transparent border-solid border-t-0 border-b-[5px] border-x-[6px] h-0 w-0 mr-[5px] self-center" v-if="item.latestPrice?.day >= 0"></div>
                        <div class="border-t-red-600 border-b-transparent border-x-transparent border-solid border-t-[6px] border-b-0 border-x-[6px] h-0 w-0 mr-[5px] self-center" v-else="item.latestPrice?.day < 0"></div>
                        <p class="m-0" :class="{ 'text-green-500': item.latestPrice?.day >= 0, 'text-red-500': item.latestPrice?.day < 0 }">{{ item.latestPrice?.day }}%</p>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </a>
          </div>
        </div>
      </div>
    </div>
    <!-- Section Under Price Table -->
    <div class="pt-12">
      <section>
        <div class="md:mt-0 md:p-8 md:border rounded-lg mt-14 pb-6 px-4">
          <h2 class="md:text-xl text-base font-semibold mb-4">About Cryptocurrencies</h2>
          <div class="md:text-base text-sm mb-6 text-slate-600">
            Cryptocurrency is a digital currency asset that is secured using the cryptography method on an open database called a blockchain. There are 2 types of crypto, namely coins and tokens. Coin is a cryptocurrency that stands on its
            own blockchain with the example of bitcoin and ethereum, while token is a cryptocurrency that "rides" on top of the blockchain of other native assets.
          </div>
          <a href="#">
            <div class="py-2 px-6 border rounded-full inline-flex md:text-base text-xs font-semibold items-center select-none">
              <span>Learn More{{ " ->" }}</span>
            </div>
          </a>
        </div>
      </section>
      <section class="mt-10 md:px-0 mx-4 md:pb-0 pb-20 grid md:grid-cols-3 grid-cols-1 gap-14">
        <div class="flex flex-col">
          <div class="mb-6">
            <div>
              <div>
                <img src="../assets/img/about-crypto-1.png" alt="about crypto" class="md:h-20 h-14 w-auto" />
              </div>
            </div>
            <h3 class="text-xl font-semibold mt-10">Why Invest in Bitcoin?</h3>
            <div class="mt-4">
              <p>The total supply of Bitcoin is limited by the Bitcoin protocol code to 21,000,000 BTC. Therefore, many investors buy and store Bitcoin long-term because they believe that later Bitcoin will become as scarce as gold.</p>
            </div>
          </div>
          <div>
            <a href="" class="text-base font-semibold">Learn More {{ "->" }}</a>
          </div>
        </div>
        <div class="flex flex-col">
          <div class="mb-6">
            <div>
              <div>
                <img src="../assets/img/about-crypto-2.png" alt="about crypto" class="md:h-20 h-14 w-auto" />
              </div>
            </div>
            <h3 class="text-xl font-semibold mt-10">What is Bitcoin and blockchain?</h3>
            <div class="mt-4">
              <p>
                Bitcoin is the first digital asset/cryptocurrency to use blockchain technology. This technology is useful for ensuring all transactions are secure and irreversible. As a digital asset on the blockchain, Bitcoin (BTC) is
                fully digital and does not have any physical form.
              </p>
            </div>
          </div>
          <div>
            <a href="" class="text-base font-semibold">Learn More {{ "->" }}</a>
          </div>
        </div>
        <div class="flex flex-col">
          <div class="mb-6">
            <div>
              <div>
                <img src="../assets/img/about-crypto-3.png" alt="about crypto" class="md:h-20 h-14 w-auto" />
              </div>
            </div>
            <h3 class="text-xl font-semibold mt-10">How to Invest Crypto at the Door?</h3>
            <div class="mt-4">
              <p>Before you invest crypto in Pintu, there are several steps that you must follow, one of which is preparing your ID card. But don't worry, because this process is easy and only takes 10 minutes.</p>
            </div>
          </div>
          <div>
            <a href="" class="text-base font-semibold">Learn More {{ "->" }}</a>
          </div>
        </div>
      </section>
    </div>
  </main>
</template>

<script setup>
import { reactive, onMounted } from "vue";
import axios from "axios";

const state = reactive({
  items: [],
});

const fetchData = async () => {
  const firstAPI = "https://api.pintu.co.id/v2/wallet/supportedCurrencies";
  const secondAPI = "/api";
  axios
    .all([axios.get(firstAPI), axios.get(secondAPI)])
    .then(
      axios.spread((apiRes1, apiRes2) => {
        apiRes1.data.payload.shift();
        state.items = apiRes1.data.payload.map((item1) => {
          const pairSelected = item1.currencySymbol;
          const item2 = apiRes2.data.payload.find((item) => item?.pair.toUpperCase().includes(pairSelected));
          const formatter = new Intl.NumberFormat("en-US", {
            minimumFractionDigits: 0,
          });
          const formattedLatestPrice = formatter.format(item2.latestPrice);
          item2.latestPrice = formattedLatestPrice;
          return {
            name: item1.name,
            symbol: item1.currencySymbol,
            logo: item1.logo,
            color: item1.color,
            latestPrice: item2,
          };
        });
      })
    )
    .catch((err) => console.log(err));
};

onMounted(async () => {
  fetchData();
  setInterval(() => {
    fetchData();
  }, 1000);
});
</script>
