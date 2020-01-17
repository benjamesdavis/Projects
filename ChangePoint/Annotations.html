"use strict";

// line chart code: https://bl.ocks.org/d3noob/402dd382a51a4f6eea487f9a35566de0
// time series from: http://bl.ocks.org/mbostock/3883245
// set the dimensions and margins of the graph
var margin = { top: 20, right: 20, bottom: 30, left: 50 },
    height = 500 - margin.top - margin.bottom;
var maxWidth = 860 - margin.left - margin.right;
var width = 860 - margin.left - margin.right;

var parseTime = d3.timeParse("%d-%b-%y");
var _x = d3.scaleTime().range([0, width]);
var _y = d3.scaleLinear().range([height, 0]);

var valueline = d3.line().x(function (d) {
  return _x(d.date);
}).y(function (d) {
  return _y(d.close);
});

var svg = d3.select("svg").attr("width", 960).attr("height", height + margin.top + margin.bottom).append("g").attr("transform", "translate(" + margin.left + "," + margin.top + ")");

d3.tsv("data.hidden.tsv", function (error, data) {
  if (error) throw error;

  data.forEach(function (d) {
    d.date = parseTime(d.date);
    d.close = +d.close;
  });

  _x.domain(d3.extent(data, function (d) {
    return d.date;
  }));
  _y.domain([0, d3.max(data, function (d) {
    return d.close;
  })]);

  svg.append("path").data([data]).attr("class", "line").attr("d", valueline);

  svg.append("g").attr("class", "x-axis").attr("transform", "translate(0," + height + ")").call(d3.axisBottom(_x));

  svg.append("g").call(d3.axisLeft(_y));

  //Add annotations
  var labels = [{
    data: { date: "9-Apr-12", close: 636.23 },
    dy: 37,
    dx: -142
  }, {
    data: { date: "26-Feb-08", close: 119.15 },
    dy: -137,
    dx: 0,
    note: { align: "middle" }
  }, {
    data: { date: "18-Sep-09", close: 185.02 },
    dy: 37,
    dx: 42
  }].map(function (l) {
    l.note = Object.assign({}, l.note, { title: "Close: " + l.data.close,
      label: "" + l.data.date });
    l.subject = { radius: 4 };

    return l;
  });

  var timeFormat = d3.timeFormat("%d-%b-%y");

  window.makeAnnotations = d3.annotation().annotations(labels).type(d3.annotationCalloutCircle).accessors({ x: function x(d) {
      return _x(parseTime(d.date));
    },
    y: function y(d) {
      return _y(d.close);
    }
  }).accessorsInverse({
    date: function date(d) {
      return timeFormat(_x.invert(d.x));
    },
    close: function close(d) {
      return _y.invert(d.y);
    }
  }).on('subjectover', function (annotation) {
    annotation.type.a.selectAll("g.annotation-connector, g.annotation-note").classed("hidden", false);
  }).on('subjectout', function (annotation) {
    annotation.type.a.selectAll("g.annotation-connector, g.annotation-note").classed("hidden", true);
  });

  svg.append("g").attr("class", "annotation-test").call(makeAnnotations);

  svg.selectAll("g.annotation-connector, g.annotation-note").classed("hidden", true);
});
