<template lang="pug">
	include ../../layout/mixins

	div.catalog
			div.container
					div.row.mb-5
							div.col-4.d-flex.align-items-center
									router-link(to='/btb' class='link-back')
											+svgIcon(12, 12, 'link-back__icon', '#two-arrow')
											span.link-back__text Вернуться к каталогам
							div.col-4
									h1.heading.heading_page Заказная сессия осень-зима 2017


					div.row.mb-5
							div.col-4.d-flex.align-items-center
									span.label Фильтр:

									selectbox(placeholder='Бренд')

									selectbox(placeholder='Товарная группа')

							div.col-4.d-flex.align-items-center
									pagination(:current="currentPage" :total='totalProducts' :perPage="perPage" @page-changed="change")
							div.col
							div.col-3
									search

					div.row.mb-5
							div.col.col-lg-4.col-xl-3.col-hd-2.catalog-item-wrapper(v-for='(item, index) in products' )
									catalog-item(:id='item.id' :title='item.title' :image='item.photos[0]' :description='item.composition' :price='item.price.opt' :key='index')

					div.row.justify-content-center.mb-5
							div.col-4
									pagination(:current="currentPage" :total='totalProducts' :perPage="perPage" @page-changed="change")


</template>

<script src='./Catalog'></script>

