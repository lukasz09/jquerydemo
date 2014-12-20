(function($) {

	var methods = {
		init : function() {
		},
		
		show : function(options) {
			var settings = $.extend({
				'text' : 'Podaj wartość'
			}, options);
			var inputText = settings.text;
			$(this).val(inputText);

			$(this).focus(function() {
				if ($(this).val() === inputText) {
					$(this).val('');
				}
			});

			$(this).blur(function() {
				if ($(this).val() === '') {
					$(this).val(inputText);
				}
			});
		},

		clear : function() {
			$(this).val = '';
		},

		update : function() {
		},
		
		require : function() {
		    $(this).on('input', function() {
                var input=$(this);
                var is_name=input.val();
                if(is_name) {
                    input.removeClass("invalid").addClass("valid");
                    $('#name_error').css('display','none');
                    $('#name_error').css('margin-left','10px');
                }
                else {
                    input.removeClass("valid").addClass("invalid");
                    $('#name_error').css('display','inline');
                    $('#name_error').css('color','red');
                    $('#name_error').css('margin-left','10px');
                }
            });
            $(this).click(function () {
               $(this).select();
            });
		},
		
		maxLength : function(length) {
			$(this).attr('maxLength', length);
			$(this).on('input', function() {
                var input=$(this);
                var len=input.val().length;
                if(len==length) {
                    $('#genre_error').css('display','inline');
                    $('#genre_error').css('color','red');
                    $('#genre_error').css('margin-left','10px');
                }
                else {
                    $('#genre_error').css('display','none');
                    $('#genre_error').css('margin-left','10px');
                }
            });
		},
		
		checkDate : function() {
		    $(this).on('input', function() {
                var input=$(this);
                var wart=input.val();
                var len=input.val().length;
                if(len==4 && wart[0]>='0' && wart[0]<='9' &&
                    wart[1]>='0' && wart[1]<='9' &&
                    wart[2]>='0' && wart[2]<='9' &&
                    wart[3]>='0' && wart[3]<='9') {
                    $('#date_error').css('display','none');
                    $('#date_error').css('margin-left','10px');
                }
                else {
                    $('#date_error').css('display','inline');
                    $('#date_error').css('color','red');
                    $('#date_error').css('margin-left','10px');
                }
            });
		}
	};

	$.fn.inputFocus = function(method) {
		var args = arguments;
		return this.each(function(){
			if (methods[method]) {
				return methods[method].apply(this, Array.prototype.slice.call(
						args, 1));
			} else if (typeof method === 'object' || !method) {
				console.log("Init!");
				return methods.init.apply(this, args);
			} else {
				$.error(" Method " + method
						+ ' does not exists on jQuery.inputFocus');
			}
		});
	};
})(jQuery);
