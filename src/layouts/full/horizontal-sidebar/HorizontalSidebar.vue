<script setup lang="ts">
import { ref, shallowRef } from 'vue'
import { useDisplay } from 'vuetify'
import { useCustomizerStore } from '@/stores/customizer'
import HorizontalItems from './horizontalItems'
import NavItem from './NavItem/Index.vue'
import NavCollapse from './NavCollapse/Index.vue'
import VerticalSidebar from '../vertical-sidebar/VerticalSidebar.vue'

const customizer = useCustomizerStore()
const sidebarMenu = shallowRef(HorizontalItems)
const { mdAndUp } = useDisplay()
// function subIsActive(input: any) {
//     const paths = Array.isArray(input) ? input : [input];
//     return paths.some((path) => {
//         return; //$route.path.indexOf(path) === 0; // current path starts with this path string
//     });
// }
</script>

<template>
	<template v-if="mdAndUp">
		<div class="horizontalMenu border-bottom">
			<!-- <div :class="customizer.boxed ? 'maxWidth' : 'px-6'">
                <ul class="gap-1 horizontal-navbar mx-0">
                    <li v-for="(item, i) in sidebarMenu" :key="i" class="navItem">
                        <NavCollapse :item="item" :level="0" v-if="item.children" />
                        <NavItem :item="item" v-else />
                    </li>
                </ul>
            </div>     -->
		</div>
	</template>
	<div v-else class="mobile-menu">
		<VerticalSidebar />
	</div>
</template>
<style lang="scss"></style>
