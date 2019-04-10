#如何遍历dom节点
  function getTextNodesDeep(elem){
    let textNodes = [];
    if(elem){
      let nodes = elem.childNodes, i = nodes.length;
      for(;i--;){
        let node = nodes[i];
        let nodeType=node.nodeType;
        if(nodeType===1){//元素节点
          if(node.id){
            if(node.title!==''){
              textNodes.push(node);
            }
          }
          textNodes = textNodes.concat(getTextNodesDeep(node))
        }
      }
    }
    return textNodes;
  }
>