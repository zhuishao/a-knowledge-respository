#vue，canvas中绘制图片
##在html中放置图片
`<img ref="conf0" src="../assets/bg@2x.png" style="display: none">`
##获取canvas和context和图片
 let drawing=document.querySelector('canvas');
            const context=drawing.getContext('2d');
            const img=document.images[0];
##加载图片
 img.onload=()=>{
                context.drawImage(img,0,0);
	}