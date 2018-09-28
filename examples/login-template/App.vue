<script>
    export default {
        onLaunch: function () {
            console.log('App Launch');
        },
        onShow: function () {
            console.log('App Show');
        },
        onHide: function () {
            console.log('App Hide');
        }
    }
</script>

<style>
    /*每个页面公共css */
    /* uni-app默认全局使用flex布局。因为flex布局有利于跨更多平台，尤其是采用原生渲染的平台。如不了解flex布局，请参考http://www.w3.org/TR/css3-flexbox/。如不使用flex布局，请删除或注释掉本行。*/
  
    page {
    	background-color: #F8F8F8;
    	height: 100%;
    	font-size: 62.5%;
    	line-height: 1.6;
    }

    .content {
        display: flex;
        flex: 1;
        flex-direction: column;
        background-color: #efeff4;
        padding: 20px;
    }
    .container{
		display: flex;
		flex: 1;
		flex-direction: column;
		background-color: #efeff4;
	}
    .input-group {
        background-color: #ffffff;
        margin-top: 40px;
        position: relative;
    }

    .input-group::before {
        position: absolute;
        right: 0;
        top: 0;
        left: 0;
        height: 1px;
        content: '';
        -webkit-transform: scaleY(.5);
        transform: scaleY(.5);
        background-color: #c8c7cc;
    }

    .input-group::after {
        position: absolute;
        right: 0;
        bottom: 0;
        left: 0;
        height: 1px;
        content: '';
        -webkit-transform: scaleY(.5);
        transform: scaleY(.5);
        background-color: #c8c7cc;
    }

    .input-row {
        display: flex;
        flex-direction: row;
        position: relative;
    }

    .input-row .title {
        width: 20%;
        height: 50px;
        min-height: 50px;
        padding: 15px 0;
        padding-left: 30px;
        line-height: 50px;
    }

    .input-row.border::after {
        position: absolute;
        right: 0;
        bottom: 0;
        left: 15px;
        height: 1px;
        content: '';
        -webkit-transform: scaleY(.5);
        transform: scaleY(.5);
        background-color: #c8c7cc;
    }

    .btn-row {
        margin-top: 50px;
        padding: 20px;
    }

    button.primary {
        background-color: #0faeff;
    }
	.grid {
		padding: 5px;
		margin-left: auto;
		margin-right: auto;
		width: 100%;
		display: -webkit-box;
		display: -webkit-flex;
		display: -ms-flexbox;
		display: flex;
		-webkit-box-orient: vertical;
		-webkit-box-direction: normal;
		-webkit-flex-direction: column;
		-ms-flex-direction: column;
		flex-direction: column;
	}
	.row {
		display: -webkit-box;
		display: -webkit-flex;
		display: -ms-flexbox;
		display: flex;
		-webkit-flex-wrap: wrap;
		-ms-flex-wrap: wrap;
		flex-wrap: wrap;
		margin-top:15px;
		margin-bottom: 15px;
	}
	.col{
		padding: 5px;
		position: relative;
		width: 100%;
		margin: 0;
		min-height: 1px;
		-webkit-flex-basis: 0;
		-ms-flex-preferred-size: 0;
		flex-basis: 0;
		-webkit-box-flex: 1;
		-webkit-flex-grow: 1;
		-ms-flex-positive: 1;
		flex-grow: 1;
		max-width: 100%;
	}
	.text-cebter{
		text-align: center;
	}
</style>
