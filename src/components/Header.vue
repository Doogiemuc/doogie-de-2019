<template>
    <header class="header">
        <nav class="nav">
			<div class="nav-sitename">
				<g-link to="/" exact>
					<img src="/logo-hands.png" />
					<h1>{{ $static.metaData.siteName }}</h1>
				</g-link>
				<h3 class="siteDescription">{{ $static.metaData.siteDescription }}</h3>
			</div>
            <div class="nav-about">
				<g-link :to="infoLink">
					{{ isInfoPage ? "home" : "about" }}
				</g-link>
            </div>
        </nav>
    </header>
</template>

<script>
export default {
    props: {
        page: {
            type: String,
            required: true
        }
    },
    computed: {
        isInfoPage() {
            return this.page === "info" && true
        },
        infoLink() {
            return this.isInfoPage ? "/" : "/info"
        }, 
    }
}
</script>

<static-query>
    query {
		metaData {
			siteName
			siteDescription
		}
    }
</static-query>

<style>

/** 
 These are the settings for small devices! 
 For devices with a viewport widht > 768px see below!!!
*/
.header h1 {
	margin: 1rem;
	font-family: Georgia, 'Times New Roman', Times, serif;
	font-weight: bold;
	letter-spacing: 1px;
}

.siteDescription {
	font-family: "Work Sans","Helvetica Neue", Helvetica, sans-serif;
	font-size: 1.0rem;
	color: #464646;
	/*letter-spacing: 0px;*/
}
  
.nav {
    padding: 0.5rem;
    border-bottom: 1px solid #EBEBEB;
	display: flex;
    justify-content: space-between;
    flex-direction: row;
	align-items: center;
}

.nav-sitename {
	width: 100%;
	text-align: center;
}

.nav img {
     margin-bottom: 0;
}

.nav-about {
	position: absolute;
	top: 10px;
	right: 10px;
	font-size: 1.0rem;
}

.nav-about a { color: #464646; }

  
@media (min-width: 768px) {
    .header {
      height: 100vh;
      position: fixed;
      left: 0;
      top: 0;
    }
    
    .nav {  
      width: 30vw;
      height: 100%;
      border-right: 1px solid #EBEBEB;
      border-bottom: none;
      flex-direction: column;
	  align-items: center;
	  justify-content: space-between;
	}
	
	.nav-sitename {
		padding-top: 2.2rem;
		
	}

	.nav-about {
		position: relative;
		top: 0;
		right: 0;
		border-top: 1px solid #EBEBEB;
		width: 100%;
		text-align: center;
		padding: 1rem 0;
	}


}
</style>