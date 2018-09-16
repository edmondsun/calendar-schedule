# Schedule
<h3>Description</h3>
    The easiest way to schedule work with mouse
    You can add new jobs or remove old ones on the fly as you please.
<h3>Image</h3>
    ![Image tag](https://github.com/edmondsun/calendar-schedule/blob/master/schedule.png)
<h3>Demo Site</h3>
   <a href="http://makodoben.github.io/Schedule">&nbsp;&nbsp; Demo Website</a>
<h3>Quick Start</h3>
  After git clone the project, add the src below
  <pre><code>
    <script language="javascript" src="./js/jquery.min.js" type="text/javascript"></script>
    <script language="javascript" src="./js/jquery-ui-1.8.11.custom.min.js" type="text/javascript"></script>
    <script language="javascript" src="./js/date.js" type="text/javascript"></script>
    <script language="javascript" src="./js/jquery.weekcalendar.js" type="text/javascript"></script>
  </code></pre>
  Give the schedule time format like this:
  <pre><code>
      scheduleArray = {
        Schedule0 : "00:00-09:00!12:00-15:00",
        Schedule1 : "05:00-09:00!13:30-17:00",
        Schedule2 : "00:00-23:59",
        Schedule3 : "00:00-23:59",
        Schedule4 : "00:00-23:59",
        Schedule5 : "00:00-23:59",
        Schedule6 : "00:00-23:59"
      }     
  </pre></code>
  Finally add the initial parameters like this:
   <pre><code>
      $('#calendar').weekCalendar({
      data: store, 
      date: new Date( 
        dateData.getFullYear(),
        parseInt(dateData.getMonth(), 10),
        dateData.getDate() 
      ),
      timeslotsPerHour: 2,
      height: function($calendar) {
        return $(window).height() - $('h1').outerHeight() - $('.description').outerHeight();
      },
      eventRender: function(calEvent, $event) {
        if (calEvent.end.getTime() < new Date().getTime()) {
          $event.css('backgroundColor', '#aaa');
          $event.find('.time').css({'backgroundColor': '#999', 'border':'1px solid #888'});
        }
      }
    });
  </code></pre>
