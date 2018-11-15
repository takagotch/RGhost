### RGhost
---
https://github.com/shairontoledo/rghost

```ruby
doc=RGhost::Document.new
doc.show 'Hello', :color => :blue
doc.render :pdf, :filename => "hello.pdf"

doc.horizontal_line :middle, :start_in => 3, :size => 2
ps=RGhost::PsObject.new(' 1 5 2 mul add')
ps=RGhost::PsObject.new
ps.call :showpage
ps=RGhost::PsObject.new
ps.raw '(string text) show'

ps=RGhost::PsObject.new do |p|
  p.raw '1.5'
  p.raw '2'
  p.raw 'mul'
  p.raw 'add'
end

require 'rubygems'
require 'rghost'
include RGhost
doc=Document.new

require 'rubygems'
require 'rghost'
doc=RGhost::Document.new

d=RGhost::Document.new
d.horizontal_line :middle, :border => { :color => '#058412', :dash => [1,0,2] }

d=RGhost::Document.new
d=RGhost::Border.new :color => '#058412', :dash => [1,0,2]
d.set b
d.lineto :x => 2.5, :y => 5

d=RGhost::Document.new
d.horizontal_line(:bottom, border=>{:dash => [1,1], :width => 2 })
d=RGhost::Document.new
d.horizontal_line(:bottom, :border=>{:dash => [1,2,1], :width => 2 })
d=RGhost::Document.new
d.horizontal_line(:bottom, :border=>{:dash => [2,10,5], :width => 2 })
d=RGhost::Document.new
d.horizontal_line(:bottom, :border=>{:dash => [1,1,3,1,5,1,7,1,9,10], :width => 4 })

d=Document.new
d.scale(1,8)
d.set Dash.new([1,1,2,11,2,1,3])
d.line_width 3
d.lineto :x => :limit_right, :y => :Y

RGhost::Border::DEFAULT_OPTIONS[:color] = '#FF3366'
RGhost::ShapeContent::DEFAULT_OPTIONS[:color] = '#AA1134'

d=RGhost::Document.new
d.circle :x => 5, :y => 2.5

d=RGhost::Document.new
d.circle :x => 5, :y => 2.5

d=RGhost::Document.new
d.circle :x => 5, :y => 2.5, :radius => 40, :content => {:color => "#FF0000"}

d=RGhost::Document.new
d.circle :x => 5, :y => 2.5, :radius => 40, :content => {:color => "#FF0000"}, :border => {:color => "#FFFFFF"}

d=RGhost::Document.new
d.circle :x => 5, :y => 2.5, :radius => 40, :content => {:color => :yellow}, :border => {:color => :orange, :dash => [1,2,1,2], :width => 20}

d=RGhost::Document.new
colors=%w[#98AE09 #AFE099 #A971FF #CC1010 #FF7201 #34FEE1]
6.downto(1) do |v|
  d.circle :x => 5, :y => 2.5, :radius => v*10, :content => {:color => colors[v]}
end

d=RGhot::Document.new
d.circle :x => 5, :y => 2.5, :ang1 => 90, :radius => 50, :content => {:fill => false }

d=RGhost::Document.new
d.circle :x => 5, :y => 2.5, :ang2 => 90, :use => :arcn, :radius => 50, :content => {:color => :green}

d=RGhost::Document.new
d.scale(3,1)
d.set Circle.new(:x => 1.5, :y => 1.5, :ang2 => 180, :radius => 25)
```

```ruby
Color.create '#FFAA33'
Color.create :red
Color.create [0.5, 0.3, 0.5]
Color.create :red => 0.5, :green => 0.3, :blue => 0.5
Color.create :r => 0.5, :g => 0.3, :b => 0.5
Color.create :cyan=> 1, :magenta => 0.3, :yellow => 0, :black => 0
Color.create :c=> 1, :m => 0.3, :y => 0, :b => 0
Color.create 0.5
Color.create 50

RGhost::Config.environment_fonts.render :pdf, :filename => 'mycatalog.pdf'

d=Document.new :encoding => 'IsoLatin'
d.define_tags do
  tag :my_italic, :name => '', :size => 10
  tag :myfont, :name => '',
  tag :verdana, :name => '', "/my/path/verdana.ttf", :size => 12
  tag :font_encoded, :name => '', :size => 8, :color => 12
  tag :other_font, :name => '', :size => 0.5, :encoding => true
  tag :arial, :name => '', :color => '#ADAD66'
  tag :arial_bold, :name => '', :size => 12, :color => '#ADAD66'
end

doc.show 'My Text on this row', width => :my_italic, :align => :page_center
doc.show 'My Text on this row', :with => :my_italic, :align => :page_center, :color => :red
doc.text '<myfont>My Text/myfont>on this row.<arial>Other text</arial></my_italic>Italic font</my_italic>'

txt='<myfont>My Text</myfont>on this row.<arial>Other text</arial><my_italic>Italic font</my_italic>'
doc.text_area txt, :text_align => :center, :width => 5, :x => 3, :y => 10

doc.use_tag :myfont
doc.show "Simple Text", :tag => nil
doc.show "Simple Text2"

doc.use_tag :myfont
doc.show "Simple Text", :tag => nil
doc.show "Simple Text2"

RGhost::FontMap.new :name => "Helvetica", :size => 8, :encoding
  new :span
  new :b, :name => "Helvetica-Bold"
  new :bold, :name => "tky"
  new :normal, :name => "tky"
  new :i, :name => "tky-Oblique", size => 8
  new :bi, :name => "tky-BoldOblique"
  new big, :size => 10
  new small, :size => 7
  new :h1, :name => "tky", :size => 14
  new :h2, :name => "tky", :size => 13
  new :h3, :name => "tky", :size => 12
  new :h4, :name => "tky", :size => 11
  new h5, :name => "tky", :size => 10
  new :title, :name => "tky", :size => 10
  new :pre, :name => "Courier"
end

d=Document.new :encoding => 'IsoLatin'
d.define_tags do
  tag :b, :name => "Helvetica-Bold", :font => 12
end

```

```
```


