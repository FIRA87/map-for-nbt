
window.onload = function () {
//$(function() {

	var w = 700;
	var h = 450;
	var R = Raphael('map');

	// default attributes
	var attributes = {
		fill: '#898989',
		stroke: '#fff',
		"stroke-width": "1",
		'stroke-linejoin': 'round'
	};

	// set with and height
	R.canvas.setAttribute('preserveAspectRatio', 'xMidYMid meet');
	R.setViewBox(0, 0, w, h, true);
	R.setSize('100%', '100%');
	//R.safari();

	arr = new Array();

	for (var country in paths) {

		var obj = R.path(paths[country].path);
		obj.attr(attributes);
		obj.attr(attributes).attr({fill: paths[country].fill});
		arr[obj.id] = country;

		// text
		/*
		var bbox = obj.getBBox();
		if(paths[arr[obj.id]].name != 'н.Мир Сайид Алии Ҳамадонӣ' &&
			//paths[arr[obj.id]].name != 'ш.Турсунзода' &&
			paths[arr[obj.id]].name != 'н.Шаҳринав' &&
			paths[arr[obj.id]].name != 'ш.Левакант' &&
			paths[arr[obj.id]].name != 'н.Ёвон' &&
			paths[arr[obj.id]].name != 'н.Ҷаббор Расулов' &&
			paths[arr[obj.id]].name != 'н.Зафаробод' &&
			paths[arr[obj.id]].name != 'ш.Бӯстон' &&
			paths[arr[obj.id]].name != 'ш.Бохтар' &&
			paths[arr[obj.id]].name != 'н.Кӯшониён' &&
			paths[arr[obj.id]].name != 'н.Хуросон' &&
			paths[arr[obj.id]].name != 'н.Темурмалик' &&
			paths[arr[obj.id]].name != 'н.Бобоҷон Ғафуров' &&
			paths[arr[obj.id]].name != 'ш.Роғун' &&
			paths[arr[obj.id]].name != 'н.Носири Хусрав' &&
			paths[arr[obj.id]].name != 'ш.Спитамен' &&
			paths[arr[obj.id]].name != 'н.Мӯъминобод' &&
			paths[arr[obj.id]].name != 'ш.Норак' &&
			paths[arr[obj.id]].name != 'ш.Ҳисор' &&
			paths[arr[obj.id]].name != 'н.Восеъ' &&
			paths[arr[obj.id]].name != 'н.Данғара' &&
			paths[arr[obj.id]].name != 'н.Абдураҳмони Ҷомӣ'
		//paths[arr[obj.id]].name != 'н.Рӯдакӣ' &&
		//paths[arr[obj.id]].name != ''
		)
		{
			R.text(bbox.x + bbox.width / 2, bbox.y + bbox.height / 2, paths[arr[obj.id]].name).attr({ "font-size": 4 });
		}
		*/

		// on hover
		obj.hover(function () {
				this.animate({
					fill: '#8fbf27'
				}, 300);

				// content
				//$('.content').html('<b>' + paths[arr[this.id]].name + '</b>' + '<br>' + paths[arr[this.id]].content).fadeIn();

				// tooltip
				/*
				var point = this.getBBox(0);
				//$('#map').next('.point').remove();
				//$('#map').after($('<div />').addClass('point'));
				$('.point').css('disply', 'table').html(paths[arr[this.id]].name).fadeIn();
				//resize();
				*/

			},
			function () {
				this.animate({
					fill: attributes.fill
				}, 300);
		});

		// on click
		obj.click(function () {

			// clear all area
			$("#map > svg > path").each(function(){
				$(this).css('fill', '#898989');
			});

			// select area
			var _obj = R.path(paths[arr[this.id]].path);
			_obj.animate({
				fill: '#8fbf27',
				stroke: '#fff'
			}, 300);

			// modal popup
			$('#exampleModalLong .modal-body').html(paths[arr[this.id]].content);
			$('#exampleModalLong #exampleModalLongTitle').html(paths[arr[this.id]].name);
			$('#exampleModalLong').modal('show');

			//console.log('qqq');

			// content
			//$('.content').html('<b>' + paths[arr[this.id]].name + '</b>' + '<br>' + paths[arr[this.id]].content).fadeIn();
		});

	}

	// on click region
	$(document).on("click",".regionData a",function(e) {
		e.preventDefault();

		var _val = $(this).attr('data-id');
		//console.log(_val);

		for (var country in paths) {

			var objR = R.path(paths[country].path);
			objR.attr(attributes).attr({fill: paths[country].fill});
			arr[objR.id] = country;

			if(paths[country].name == _val){

				// select area
				var _obj = R.path(paths[country].path);
				_obj.animate({
					fill: '#8fbf27',
					stroke: '#fff'
				}, 300);

				// modal popup
				$('#exampleModalLong .modal-body').html(paths[country].content);
				$('#exampleModalLong #exampleModalLongTitle').html(paths[country].name);
				$('#exampleModalLong').modal('show');

			}

			// on hover
			objR.hover(function () {
				this.animate({
					fill: '#8fbf27'
				}, 300);
			},
			function () {
				this.animate({
					fill: attributes.fill
				}, 300);
			});

			// on click
			objR.click(function () {

				// clear all area
				$("#map > svg > path").each(function(){
					$(this).css('fill', '#898989');
				});

				// click
				var _obj = R.path(paths[arr[this.id]].path);
				_obj.animate({
					fill: '#8fbf27',
					stroke: '#fff'
				}, 300);

				// modal popup
				$('#exampleModalLong .modal-body').html(paths[arr[this.id]].content);
				$('#exampleModalLong #exampleModalLongTitle').html(paths[arr[this.id]].name);
				$('#exampleModalLong').modal('show');

			});

		}

	});

	// on change
	$('#region_list').on('change', function() {

		var _val = this.value;

		for (var country in paths) {

			var objR = R.path(paths[country].path);
			objR.attr(attributes).attr({fill: paths[country].fill});
			arr[objR.id] = country;

			if(paths[country].name == _val){
				// select area
				var _obj = R.path(paths[country].path);
				_obj.animate({
					fill: '#8fbf27',
					stroke: '#fff'
				}, 300);
			}

			// on hover
			objR.hover(function () {
					this.animate({
						fill: '#8fbf27'
					}, 300);
				},
				function () {
					this.animate({
						fill: attributes.fill
					}, 300);
			});

			// on click
			objR.click(function () {

				// clear all area
				$("#map > svg > path").each(function(){
					$(this).css('fill', '#898989');
				});

				// click
				var _obj = R.path(paths[arr[this.id]].path);
				_obj.animate({
					fill: '#8fbf27',
					stroke: '#fff'
				}, 300);

				// modal popup
				$('#exampleModalLong .modal-body').html(paths[arr[this.id]].content);
				$('#exampleModalLong #exampleModalLongTitle').html(paths[arr[this.id]].name);
				$('#exampleModalLong').modal('show');

			});

		}

	});

//});

}

