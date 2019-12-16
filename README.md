# jquery.countdown.js
JQuery Countdown Plugin

# Добавляем на страницу элемент, где будем показывать таймер (зададим время 1 час):

<span class="countdown" data-seconds="3600"></span>

# Инициализируем счетчик

$(function(){
	$(".countdown").each(function(index){
		var counter = $(this);
		counter.countdown({
			seconds:counter.data("seconds"),
			callback:function(days,hours,minutes,seconds,total){
				days = (days) ? days+":" : "";
				hours = (hours) ? ((hours<10)?"0"+hours:hours)+":" : "00:";
				minutes = (minutes) ? ((minutes<10)?"0"+minutes:minutes)+":" : "00:";
				seconds = (seconds) ? ((seconds<10)?"0"+seconds:seconds) : "00";
				counter.html(days+hours+minutes+seconds);
			},
			finished:function(){
				alert("Таймер оттаймерил!");
			}
		});
	});
});
