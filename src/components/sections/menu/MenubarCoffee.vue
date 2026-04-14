<template>
  <Tabs default-value="cold-coffee" class="w-full lg:w-260 mt-10">
    <TabsList
      class="flex flex-nowrap h-auto pl-5 items-center justify-start md:justify-center gap-2 px-3 py-2 w-full md:max-w-fit mx-auto overflow-x-auto scrollbar-none bg-accent rounded-2xl"
    >
      <TabsTrigger value="cold-coffee">
        <h4>Cold Coffee</h4>
      </TabsTrigger>
      <TabsTrigger value="basic-coffee">
        <h4>Basic Coffee</h4>
      </TabsTrigger>

      <TabsTrigger value="hot-drinks">
        <h4>Hot Drink</h4>
      </TabsTrigger>

      <TabsTrigger value="cold-drinks">
        <h4>Cold Drink</h4>
      </TabsTrigger>

      <TabsTrigger value="heavy-food">
        <h4>Heavy Food</h4>
      </TabsTrigger>

      <TabsTrigger value="snack">
        <h4>Snack</h4>
      </TabsTrigger>
    </TabsList>
    <!-- COLD COFFEE -->
    <TabsContent value="cold-coffee" class="menu-grid">
      <MenuList :menu="menuItem1" class="order-2 lg:order-1" />
      <div class="menu-img-wrapper mt-6 order-1"><img :src="menu1" class="menu-img-inner" /></div>

      <div class="menu-img-wrapper order-3"><img :src="menu2" class="menu-img-inner" /></div>
      <MenuList :menu="menuItem2" class="order-4" />
    </TabsContent>

    <!-- BASIC COFFEE -->
    <TabsContent value="basic-coffee" class="menu-grid">
      <MenuList :menu="menuItem3" class="order-2 lg:order-1" />
      <div class="menu-img-wrapper mt-6 order-1">
        <img :src="menu3" class="menu-img-inner scale-100!" />
      </div>

      <div class="menu-img-wrapper order-3"><img :src="menu4" class="menu-img-inner" /></div>
      <MenuList :menu="menuItem4" class="order-4" />
    </TabsContent>

    <!-- HOT DRINK -->
    <TabsContent value="hot-drinks" class="menu-grid">
      <MenuList :menu="menuItem5" class="order-2 lg:order-1" />
      <div class="menu-img-wrapper order-1">
        <img :src="wedang" class="menu-inner-img scale-125!" />
      </div>

      <div class="menu-img-wrapper order-3"><img :src="milk" class="menu-img-inner" /></div>
      <MenuList :menu="menuItem6" class="order-4" />
    </TabsContent>

    <!-- COLD DRINK -->
    <TabsContent value="cold-drinks" class="menu-grid">
      <MenuList :menu="menuItem7" class="order-2 lg:order-1" />
      <div class="menu-col order-1">
        <div class="menu-img-wrapper mt-6"><img :src="menu5" class="menu-img-inner" /></div>
        <MenuList :menu="menuItem8" class="" />
      </div>
    </TabsContent>

    <!-- HEAVY FOOD -->
    <TabsContent value="heavy-food" class="menu-grid">
      <div class="menu-col flex-col-reverse! lg:flex-col! order-2 lg:order-1">
        <MenuList :menu="menuItem9" />
        <div class="menu-img-wrapper mt-6"><img :src="menu6" class="menu-img-inner" /></div>
      </div>

      <div class="menu-col order-1">
        <div class="menu-img-wrapper"><img :src="menu7" class="menu-img-inner" /></div>
        <MenuList :menu="menuItem10" />
      </div>
    </TabsContent>

    <!-- SNACK (SPECIAL LAYOUT) -->
    <TabsContent value="snack" class="menu-grid">
      <div class="menu-col flex-col-reverse! lg:flex-col! order-2 lg:order-1">
        <MenuList :menu="menuItem11" />
        <div class="menu-img-wrapper"><img :src="menu9" class="menu-img-inner" /></div>
      </div>

      <div class="menu-col order-1">
        <div class="menu-img-wrapper translate-y-4 mb-2">
          <img :src="menu8" class="menu-img-inner" />
        </div>
        <MenuList :menu="menuItem12" />
      </div>
    </TabsContent>
  </Tabs>
</template>

<style scoped>
@reference '@/assets/main.css';
.menu-grid {
  @apply grid 
         grid-cols-1 
         lg:grid-cols-[minmax(0,520px)_minmax(0,520px)]
         justify-center
         gap-8 md:gap-12 
         mt-10 md:mt-14 
         items-center! justify-items-center;
}

.menu-img-wrapper {
  @apply w-full max-w-[520px] overflow-hidden rounded-xl;
}

.menu-img-inner {
  @apply w-full h-full object-cover scale-110;
}

.menu-col {
  @apply flex flex-col w-full justify-between! items-center h-full gap-12 lg:gap-8;
}
</style>

<script setup lang="ts">
import { Tabs, TabsContent, TabsList, TabsTrigger } from '@/components/ui/tabs'
import MenuList from './MenuList.vue'
import menu1 from '@/assets/images/menu/menu1.png'
import menu2 from '@/assets/images/menu/menu2.png'
import menu3 from '@/assets/images/menu/menu3.png'
import menu4 from '@/assets/images/menu/menu4.png'
import menu5 from '@/assets/images/menu/menu5.png'
import menu6 from '@/assets/images/menu/menu6.png'
import menu7 from '@/assets/images/menu/menu7.png'
import menu8 from '@/assets/images/menu/menu8.png'
import menu9 from '@/assets/images/menu/menu9.png'
import milk from '@/assets/images/menu/milk.png'
import wedang from '@/assets/images/menu/wedang.png'

const menuItem1 = [
  {
    name: 'Americano',
    contents: 'Biji arabika + biji robusta',
    price: '17.00',
  },
  {
    name: 'V60',
    contents: 'Biji arabica',
    price: '17.50',
  },
  {
    name: 'Sweet Italian',
    contents: 'Kopi + susu',
    price: '18.00',
  },
  {
    name: 'Es Kopi',
    contents: 'Sirup tiramisu + susu + kopi',
    price: '16.00',
  },
  {
    name: 'Es Kopi Gadoe',
    contents: 'Sirup caramel + susu + kopi',
    price: '15.50',
  },
]

const menuItem2 = [
  {
    name: 'Es Kopi Gula Aren',
    contents: 'Sirup gula aren + susu + kopi',
    price: '17.50',
  },
  {
    name: 'Es Kopi Milo',
    contents: 'Bubuk milo + susu + kopi',
    price: '17.00',
  },
  {
    name: 'Es Kopi Taro',
    contents: 'Sirup caramel + bubuk taro + susu + kopi',
    price: '18.00',
  },
  {
    name: 'Es Kopi Matcha',
    contents: 'Sirup tiramisu + bubuk matcha + susu + kopi',
    price: '18.00',
  },
  {
    name: 'Es Kopi Red Velvet',
    contents: 'Sirup tiramisu + bubuk matcha + susu + kopi',
    price: '18.00',
  },
]

const menuItem3 = [
  {
    name: 'Tubruk Gardoe',
    contents: 'Biji robusta + bubuk sidomukti giras',
    price: '12.00',
  },
  {
    name: 'Tubruk Arabica',
    contents: 'Biji arabica',
    price: '14.50',
  },
  {
    name: 'Tubruk Susu Gardoe',
    contents: 'Biji robusta + bubuk sidomukti giras + susu',
    price: '13.00',
  },
  {
    name: 'Tubruk Susu Robusta',
    contents: 'Biji robusta + bubuk sidomukti giras + susu',
    price: '14.00',
  },
  {
    name: 'Tubruk Gula Aren Robusta',
    contents: 'Sirup gula aren + biji robusta',
    price: '14.00',
  },
]

const menuItem4 = [
  {
    name: 'Tubruk Drips Arabica',
    contents: 'Biji arabica + susu',
    price: '15.00',
  },
  {
    name: 'Kopi Butter Robusta',
    contents: 'Butter + biji robusta',
    price: '16.50',
  },
  {
    name: 'Kopi Santan Robusta',
    contents: 'Santan + biji robusta',
    price: '14.50',
  },
  {
    name: 'Kopi Drips Vietnamese',
    contents: 'Biji robusta + susu',
    price: '17.00',
  },
  {
    name: 'Cappucino Gardoe 77',
    contents: 'Espresso + susu',
    price: '18.00',
  },
]

const menuItem5 = [
  {
    name: 'STMJ Jumbo Gardoe',
    contents: 'Susu + telor + madu + jahe',
    price: '18.50',
  },
  {
    name: 'Wedang Jahe Kayu Manis',
    contents: 'Biji arabica',
    price: '9.50',
  },
  {
    name: 'Teh Kayu Manis',
    contents: 'Teh + gula + kayu manis',
    price: '7.00',
  },
  {
    name: 'Susu Jahe Kayu Manis',
    contents: 'Jahe + kayu manis + susu + gula',
    price: '12.50',
  },
  {
    name: 'Susu Coklat',
    contents: 'Bubuk susu coklat + susu',
    price: '15.50',
  },
]

const menuItem6 = [
  {
    name: 'Susu Putih',
    contents: 'Bubuk susu putih + susu',
    price: '13.50',
  },
  {
    name: 'Susu Coklat Crum',
    contents: 'Bubuk coklat + susu + oreo crus',
    price: '16.50',
  },
  {
    name: 'Jeruk Hangat',
    contents: 'Sirup jeruk + gula',
    price: '9.00',
  },
  {
    name: 'Milo',
    contents: 'Bubuk milo + susu',
    price: '16.00',
  },
]

const menuItem7 = [
  {
    name: 'Teh Leci / Strawberry',
    contents: 'Teh + gula + sirup leci / strawberry',
    price: '14.00',
  },
  {
    name: 'Teh Gardoe',
    contents: 'Teh + gula',
    price: '8.50',
  },
  {
    name: 'Lemon Tea',
    contents: 'Teh + gula + sirup lemon',
    price: '15.00',
  },
  {
    name: 'Es Jeruk',
    contents: 'Gula + sirup jeruk',
    price: '9.50',
  },
  {
    name: 'Joshua Jumbo',
    contents: 'Extrajos + soda + susu',
    price: '15.50',
  },
  {
    name: 'Matcha Bloom',
    contents: 'Bubuk matcha + susu',
    price: '17.50',
  },
  {
    name: 'Nilla Trem',
    contents: 'Sirup tiramisu + susu + oreo crum',
    price: '16.00',
  },
  {
    name: 'Caramel Crum',
    contents: 'Sirup caramel + susu + oreo crum',
    price: '16.00',
  },
  {
    name: 'Pink Bu',
    contents: 'Sirup strawberry + susu + oreo crum',
    price: '17.00',
  },
  {
    name: 'Coklat Crum',
    contents: 'Bubuk coklat + susu + oreo crum',
    price: '16.00',
  },
  {
    name: 'Milo Crum',
    contents: 'Bubuk milo + susu + oreo crum',
    price: '14.00',
  },
]

const menuItem8 = [
  {
    name: 'Milo Melayu',
    contents: 'Bubuk milo + susu + topping milo',
    price: '17.00',
  },
  {
    name: 'Coklat Gardoe',
    contents: 'Bubuk coklat + susu',
    price: '16.00',
  },
  {
    name: 'Mojito',
    contents: 'Sirup strawberry + soda',
    price: '14.00',
  },
  {
    name: 'Ocean blue',
    contents: 'Sirup blue curacou + soda',
    price: '15.00',
  },
  {
    name: 'Soda Gembira Jumbo',
    contents: 'Sirup cocopandan + susu + soda',
    price: '16.00',
  },
]

const menuItem9 = [
  {
    name: 'Lalapan Ayam Goreng Sambel Kecap',
    contents: 'Ayam goreng + nasi + sambal kecap',
    price: '17.50',
  },
  {
    name: 'Lalapan Telor Tempe Sambel Kecap',
    contents: 'Telor dadar + tempe + nasi + sambel kecap',
    price: '15.50',
  },
  {
    name: 'Chicken Katshu',
    contents: 'Ayam katshu + nasi + saos',
    price: '19.50',
  },
  {
    name: 'Tahu Telor Pop Gardoe',
    contents: 'Tahu telor + nasi + bumbu kacang + kerupuk',
    price: '15.50',
  },
]

const menuItem10 = [
  {
    name: 'Omelete Saurus',
    contents: 'Mie campur telor + saos + nasi',
    price: '14.50',
  },
  {
    name: 'Mie Gardoe Goreng / Kuah',
    contents: 'Mie goreng / mie kuah + saos + sayur',
    price: '11.50',
  },
  {
    name: 'Telor',
    contents: 'Telor goreng / telor rebus',
    price: '4.50',
  },
  {
    name: 'Nasi',
    contents: 'Nasi Putih',
    price: '4.50',
  },
]

const menuItem11 = [
  {
    name: 'French Fries',
    contents: 'Kentang goreng + saos',
    price: '17.00',
  },
  {
    name: 'Snack Mix',
    contents: 'Kentang goreng + nugget + sosis',
    price: '17.50',
  },
  {
    name: 'Snack Mix Special',
    contents: 'Kentang goreng + nugget + sosis + nugget ayam',
    price: '18.00',
  },
  {
    name: 'Jemblem',
    contents: 'Jemblem goreng 4 biji',
    price: '16.00',
  },
  {
    name: 'Burger Ayam',
    contents: 'Roti + daging ayam + sayur + keju + saos',
    price: '15.50',
  },
  {
    name: 'Union Ring',
    contents: 'Bawang bombay + saos',
    price: '18.00',
  },
  {
    name: 'Sosis Bakar Jumbo',
    contents: 'Sosis bakar mix saos',
    price: '18.00',
  },
]

const menuItem12 = [
  {
    name: 'Burger Sapi',
    contents: 'Roti + daging sapi + sayur + keju + saos',
    price: '17.50',
  },
  {
    name: 'Roti Bakar',
    contents: 'Roti bakar + selai coklat / vanilla / strawberry / bluberry',
    price: '17.00',
  },
  {
    name: 'Roti Bakar Ice Cream',
    contents: 'Roti bakar + ice cream',
    price: '18.00',
  },
  {
    name: 'Ice Cream',
    contents: 'Ice cream vanila / coklat / strawberry',
    price: '18.00',
  },
  {
    name: 'Tempe Mendoan',
    contents: 'Tempe mendoan + saos',
    price: '18.00',
  },
  {
    name: 'Tahu Crispy',
    contents: 'Tahu crispy + bubuk jagung manis, balado, pedas',
    price: '18.00',
  },
  {
    name: 'Cireng Goreng',
    contents: 'Cireng goreng + bumbu rujak',
    price: '18.00',
  },
]
</script>
