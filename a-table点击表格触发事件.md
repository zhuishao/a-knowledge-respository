#a-table点击表格触发事件
	<a-table
	    :columns="columns"
	    :dataSource="dataSource"
	    :customRow="cusTomRow"
	></a-table>
	          
	cusTomRow(record) {
      return {
        on: {
          click: () => {
            console.log(record.test);
            const routeUrl = this.$router.resolve({
              name: 'text',
              query: { id: 96 },
            });
            window.open(routeUrl.href, '_blank');
          },
        },
      };
    },