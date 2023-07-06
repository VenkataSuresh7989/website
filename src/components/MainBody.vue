<template>
	<div>
		<div class="banner-container">
			<b-carousel id="carousel-1" v-model="slide" :interval="4000" fade controls indicators background="#ababab" img-width="1024" img-height="480" style="text-shadow: 1px 1px 2px #333;" @sliding-start="onSlideStart" @sliding-end="onSlideEnd">
				<b-carousel-slide caption="First slide" text="Nulla vitae elit libero, a pharetra augue mollis interdum." img-src="https://picsum.photos/1024/480/?image=52"></b-carousel-slide>
				<b-carousel-slide img-src="https://picsum.photos/1024/480/?image=54">
					<h1>Hello world!</h1> 
                </b-carousel-slide>
				<b-carousel-slide img-src="https://picsum.photos/1024/480/?image=58"></b-carousel-slide>
				<b-carousel-slide>
					<template #img> <img class="d-block img-fluid w-100" width="1024" height="480" src="https://picsum.photos/1024/480/?image=55" alt="image slot"> </template>
				</b-carousel-slide>
				<b-carousel-slide caption="Blank Image" img-blank img-alt="Blank image">
					<p> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse eros felis, tincidunt a tincidunt eget, convallis vel est. Ut pellentesque ut lacus vel interdum. </p>
				</b-carousel-slide>
			</b-carousel>
		</div>
		<section id="aboutUs" class="secPad">
			<div class="container">
				<div class="heading text-center">
					<h2>Hi I'm <span :style="{ color: 'rgb(21 60 109)' }">M. Venkata Suresh</span>, a passionate UI developer</h2>
					<p>With expertise in creating visually appealing and user-friendly interfaces. I have a keen eye for design and a strong understanding of user experience principles.</p>
				</div>
				<div class="row">
					<div class="col-md-4 text-center tileBox">
						<div class="txtHead">
							<font-awesome-icon :icon="['fab', 'java']" />
							<h3>JAVA</h3> 
                        </div>
					</div>
					<div class="col-md-4 text-center tileBox">
						<div class="txtHead">
							<font-awesome-icon :icon="['fab', 'css3']" />
							<h3>HTML5/CSS3</h3> 
                        </div>
					</div>
					<div class="col-md-4 text-center tileBox">
						<div class="txtHead">
							<font-awesome-icon :icon="['far', 'lightbulb']" />
							<h3>JavaScript</h3> 
                        </div>
					</div>
				</div>
				<div class="row mt-5">
					<div class="col-md-4 text-center tileBox">
						<div class="txtHead">
							<font-awesome-icon :icon="['fas', 'desktop']" />
							<h3>Responsive <span class="id-color">Design</span></h3> 
                        </div>
					</div>
					<div class="col-md-4 text-center tileBox">
						<div class="txtHead">
							<font-awesome-icon :icon="['fab', 'react']" />
							<h3>React Js</h3> 
                        </div>
					</div>
					<div class="col-md-4 text-center tileBox">
						<div class="txtHead">
							<font-awesome-icon :icon="['fab', 'vuejs']" />
							<h3>Vue Js</h3> 
                        </div>
					</div>
				</div>
			</div>
		</section>
		<!--Skills-->
		<section id="projects" class="secPad">
			<div class="container">
				<div class="heading text-center">
					<h2>Projects</h2> 
                </div>
				<div class="mansory">
					<div class="card" v-for="(cardInfo, cIdx) in getProjectInfo" :key="cIdx">
						<div class="card-body">
							<h5 class="card-title">{{ cardInfo.name }}</h5>
							<p class="card-text"> <span>Technology : {{ cardInfo.technology }}</span>
								<br /> <span>Version : {{ cardInfo.version }}</span> 
                            </p>
							<div class="d-sm-flex justify-content-between"> <a :href="getPreview(cIdx + 1)" class="card-link">Preview</a> <a :href="getProjeCt(cIdx + 1)" class="card-link">Code</a> </div>
						</div>
					</div>
				</div>
			</div>
		</section>
		<!--Experience-->
		<section id="experience" class="secPad">
			<div class="container">
				<div class="heading text-center">
					<h2>Professional Experience</h2>
					<p>Lorem ipsum dolor sit amet, consectetur adipiscing</p>
				</div>
				<div id="timeline">
					<div class="row timeline-movement timeline-movement-top">
						<div class="timeline-badge timeline-future-movement">
							<a> <span><font-awesome-icon :icon="['fas', 'plus']" /></span> </a>
						</div>
						<div class="timeline-badge timeline-filter-movement">
							<a> 
                                <span>
                                    <font-awesome-icon :icon="['far', 'clock']" />
                                </span> 
                            </a>
						</div>
					</div>
					<div class="row timeline-movement">
						<div class="timeline-badge"> <span class="timeline-balloon-date-day">Feb</span> <span class="timeline-balloon-date-month">2014</span> </div>
						<div class="col-sm-6  timeline-item">
							<div class="row">
								<div class="col-sm-11">
									<div class="timeline-panel credits">
										<ul class="timeline-panel-ul">
											<li><span class="importo">Mussum ipsum cacilds</span></li>
											<li><span class="causale">Lorem ipsum dolor sit amet, consectetur adipiscing elit. </span> </li>
											<li>
												<p><small class="text-muted"> 18/02/2014 - Present</small></p>
											</li>
										</ul>
									</div>
								</div>
							</div>
						</div>
						<div class="col-sm-6  timeline-item">
							<div class="row">
								<div class="offset-sm-1 col-sm-11">
									<div class="timeline-panel debits">
										<ul class="timeline-panel-ul">
											<li><span class="importo">Mussum ipsum cacilds</span></li>
											<li><span class="causale">Lorem ipsum dolor sit amet, consectetur adipiscing elit. </span> </li>
											<li>
												<p><small class="text-muted"> 18/02/2014 - Present</small></p>
											</li>
										</ul>
									</div>
								</div>
							</div>
						</div>
					</div>
					<div class="row timeline-movement">
						<div class="timeline-badge"> <span class="timeline-balloon-date-day">Mar</span> <span class="timeline-balloon-date-month">2013</span> </div>
						<div class="offset-sm-6 col-sm-6  timeline-item">
							<div class="row">
								<div class="offset-sm-1 col-sm-11">
									<div class="timeline-panel debits">
										<ul class="timeline-panel-ul">
											<li><span class="importo">Mussum ipsum cacilds</span></li>
											<li><span class="causale">Lorem ipsum dolor sit amet, consectetur adipiscing elit. </span> </li>
											<li>
												<p><small class="text-muted"> 10/03/2013 - 18/02/2014</small></p>
											</li>
										</ul>
									</div>
								</div>
							</div>
						</div>
						<div class="col-sm-6  timeline-item">
							<div class="row">
								<div class="col-sm-11">
									<div class="timeline-panel credits">
										<ul class="timeline-panel-ul">
											<li><span class="importo">Mussum ipsum cacilds</span></li>
											<li><span class="causale">Lorem ipsum dolor sit amet, consectetur adipiscing elit. </span> </li>
											<li>
												<p><small class="text-muted"> 10/03/2013 - 18/02/2014</small></p>
											</li>
										</ul>
									</div>
								</div>
							</div>
						</div>
					</div>
					<div class="row timeline-movement">
						<div class="timeline-badge"> <span class="timeline-balloon-date-day">Jan</span> <span class="timeline-balloon-date-month">2010</span> </div>
						<div class="offset-sm-6 col-sm-6  timeline-item">
							<div class="row">
								<div class="offset-sm-1 col-sm-11">
									<div class="timeline-panel debits">
										<ul class="timeline-panel-ul">
											<li><span class="importo">Mussum ipsum cacilds</span></li>
											<li><span class="causale">Lorem ipsum dolor sit amet, consectetur adipiscing elit. </span> </li>
											<li>
												<p><small class="text-muted"> 11/01/2010 - 10/03/2013</small></p>
											</li>
										</ul>
									</div>
								</div>
							</div>
						</div>
						<div class="col-sm-6  timeline-item">
							<div class="row">
								<div class="col-sm-11">
									<div class="timeline-panel credits">
										<ul class="timeline-panel-ul">
											<li><span class="importo">Mussum ipsum cacilds</span></li>
											<li><span class="causale">Lorem ipsum dolor sit amet, consectetur adipiscing elit. </span>
                                            </li>
											<li>
												<p><small class="text-muted"> 11/01/2010 - 10/03/2013</small></p>
											</li>
										</ul>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</section>
		<section class="page-section section appear clearfix secPad" id="portfolio">
			<div class="container">
				<div class="heading text-center">
					<h2>Portfolio</h2>
					<p style="color:#ccc">At lorem Ipsum available, but the majority have suffered alteration in some form by injected humour.</p>
				</div>
				<div class="row">
					<div class="col-12 text-center">
						<div class="fltrbtns">
							<button :id="'getIdx' + key" v-for="(val, key) in option.getFilterData" :key="key" @click="filter(key)">{{ key }}</button>
						</div>
						<isotope ref="isotope" :list="list" :options="option">
							<div v-for="element in list" :key="element.id" class="isoDefault"> <img src="../assets/minion.jpg" alt=""> </div>
						</isotope>
					</div>
				</div>
			</div>
		</section>
	</div>
</template>
<script>
import isotope from 'vueisotope'
export default {
    name: 'MainBody',
    data() {
        return {
            slide: 0,
            getIdx: "",
            sliding: null,
            list: [
                { name: "Element1", id: 1, value: 1 },
                { name: "Element2", id: 2, value: 1 },
                { name: "Element3", id: 3, value: 4 },
                { name: "Element4", id: 4, value: 4 },
                { name: "Element5", id: 5, value: 1 },
                { name: "Element6", id: 6, value: 7 },
                { name: "Element7", id: 7, value: 7 },
                { name: "Element8", id: 8, value: 7 },
                { name: "Element9", id: 9, value: 9 }
            ],
            filterOption: "test",
            option: {
                getFilterData: {
                    all: function (item) {
                        console.log(item);
                        return true;
                    },
                    category1: function (item) {
                        return item.id === 1;
                    },
                    category5: function (item) {
                        return item.id === 5;
                    },
                    category9: function (item) {
                        return item.id === 9;
                    },
                    "category 2 4 7": function (item) {
                        return item.id === 2 || item.id === 4 || item.id === 7;
                    }
                }
            },
            getProjectInfo: [
                {
                    "name": "CRUD Operations",
                    "technology": "Vue.js",
                    "version": "2.0",
                },
                {
                    "name": "Vuex CRUD Operations",
                    "technology": "Vue.js",
                    "version": "2.0",
                },
                {
                    "name": "Trade Ticket",
                    "technology": "React.js",
                    "version": "0.1.0",
                }
            ]
        };
    },
    components: { isotope, },
    mounted() {
        this.getIdx = 'getIdxall';
        document.getElementById('getIdxall').classList.add('active');
    },
    methods: {
        onSlideStart() {
            this.sliding = true
        },
        onSlideEnd() {
            this.sliding = false
        },
        filter: function (key) {
            let idx = 'getIdx' + key.toString();

            if (document.getElementById(idx) != undefined && document.getElementById(idx) != null) {
                if (document.getElementById(this.getIdx) != undefined && document.getElementById(this.getIdx) != null) {
                    document.getElementById(this.getIdx).classList.remove('active');
                    this.getIdx = idx;
                    document.getElementById(idx).classList.add('active');
                }
                else {
                    this.getIdx = idx;
                    document.getElementById(idx).classList.add('active');
                }
            }

            this.$refs.isotope.filter(key);
        },
        getPreview: function (idx) {
            let getUrl = "https://tradeticket.netlify.app/#/";
            switch (idx) {
                case 1:
                    {
                        getUrl = "https://tradeticket.netlify.app/#/";
                    }
                    break;
                case 2:
                    {
                        getUrl = "https://tradeticket.netlify.app/#/";
                    }
                    break;
                default:
                    {
                        getUrl = "https://tradeticket.netlify.app/#/";
                    }
                    break;
            }
            return getUrl;
        },
        getProjeCt: function (idx) {
            let getUrl = "https://github.com/VenkataSuresh7989/vue-crud-operation";
            switch (idx) {
                case 1:
                    {
                        getUrl = "https://github.com/VenkataSuresh7989/vue-crud-operation";
                    }
                    break;
                case 2:
                    {
                        getUrl = "https://github.com/VenkataSuresh7989/vuex-crud-operations";
                    }
                    break;
                case 3:
                    {
                        getUrl = "https://github.com/VenkataSuresh7989/TradeTicket";
                    }
                    break;
                default:
                    {
                        getUrl = "https://github.com/VenkataSuresh7989/vue-crud-operation";
                    }
                    break;
            }
            return getUrl;
        },
    }
}
</script>

<style scoped>
.item {
    background-color: #eee;
    padding: 10px;
    width: 100%;
    height: 200px;
    font-family: monospace;
    color: #333;
    margin: 5px;
    margin-bottom: 10px;
    box-sizing: border-box;
}

@media screen and (min-width: 540px) {
    .item {
        width: calc(100% / 3 - 20px);
    }
}

.isoDefault {
    height: 200px;
}

button {
    margin-bottom: 40px;
    margin-right: 10px;
    padding: 10px;
}
</style>