'use strict';

$(document).ready(function () {

	var text_area = $('.text_area').val();
	var hidden = $('.hidden');

	function my_function() {

		//var html = $('.text_area').html().text();

		//$('.text_area').html(html).text();
		//Sets the value as the HTML
		var text = $('#text_area').val();
		text = add_links(text);
		var html = $('#text_area').html(text).text();

		//Output is the html text which goes through format_code
		$('.output').html(format_code(html));
	}

	function add_links(code) {

		$('.hidden').html(code);
		$('.hidden').find('style').remove();

		//REMOVES TD's And TABLES
		$('table').each(function () {
			$(this).replaceWith('<div>' + $(this).html() + '</div>');
			$(this).find('td').each(function () {
				$(this).replaceWith('<span>' + $(this).html() + '</span>');
			});
		});

		//runs through each a tag available
		$('.hidden a').each(function () {

			//Find the child

			if ($(this).children().is('img')) {
				console.log('IMAGES!');
			} else {
				var link = $(this).attr('href');
				var link_text = $(this).text();
				console.log(link_text);
				var final_link = link_text + '\n' + '( ' + link + ' )';
				$(this).replaceWith(final_link);
			}
		});

		code = $('.hidden').html();

		console.log('this runs the add_links');
		return code;
	}

	function format_code(html) {

		//replace style tag
		var formatted_text = html.replace(/<\/?[^>]+(>|$)/g, '');
		//replace 2 new lines
		formatted_text = formatted_text.replace(/(\r\n|\r|\n){2,}/g, '$1\n');
		//replace 3 new lines / add break
		formatted_text = formatted_text.replace(/\n\s*\n\s*\n/g, '\n\n------------------------------------------------------------------------\n\n');
		//replace with break
		formatted_text = formatted_text.replace(/(?:\r\n|\r|\n)/g, '<br />');
		return format_breaks(formatted_text);
	}

	function format_breaks(formatable_text) {
		// formatable_text = formatable_text.replace(/\n\s*\n/g, '\n');
		return formatable_text;
	}

	$('#text_area').click(function () {
		$(this).text('');
	});

	$('.button').click(function () {

		my_function();
	});
});
//# sourceMappingURL=main.js.map
