
## Other Fields (Create)
```

<div class="four wide column">
   <h4><i class="external icon"></i>URL</h4>
</div>
<div class="twelve wide column @if($errors->has('url')) error @endif">
  <div class="ui fluid corner labeled input">
    <input type="text" id="url-field" name="url" class="ui input" value="{{ old("url") }}" placeholder="https://"/>
    <div class="ui corner label">
      <i class="asterisk icon"></i>
    </div>
  </div>
       @if($errors->has("url"))
        <span class="ui pointing red basic label">{{ $errors->first("url") }}</span>
       @endif
</div>
<div class="four wide column">
   <h4><i class="folder icon"></i>Type</h4>
</div>
<div class="twelve wide column @if($errors->has('type')) error @endif">
  <select id="type-field" name="type" class="ui fluid search selection dropdown"/>
    @foreach ($types as $type)
    <option name="type" value="{{$type->id}}">{{$type->type_name}}</option>
    @endforeach
  </select>
  @if($errors->has("type"))
    <span class="ui pointing red basic label">{{ $errors->first("type") }}</span>
   @endif
</div>
<div class="four wide column">
   <h4><i class="marker icon"></i>Status</h4>
</div>
<div class="twelve wide column @if($errors->has('status')) error @endif">
  <select id="status-field" name="status" class="ui fluid search selection dropdown"/>
      @foreach ($statuses as $status)
      <option name="type" value="{{$status->id}}">{{$status->status_name}}</option>
      @endforeach

    </select>
    @if($errors->has("status"))
    <span class="ui pointing red basic label">{{ $errors->first("status") }}</span>
   @endif
</div>
<div class="four wide column">
   <h4><i class="folder outline icon"></i>Product Group</h4>
</div>
<div class="twelve wide column @if($errors->has('product_group')) error @endif">
  <select id="product_group-field" name="product_group" class="ui fluid search selection dropdown"/>
      @foreach ($product_groups as $product_group)
      <option name="product_group" value="{{$product_group->id}}">{{$product_group->product_group_name}}</option>
      @endforeach

    </select>
     @if($errors->has("product_group"))
      <span class="ui pointing red basic label">{{ $errors->first("product_group") }}</span>
     @endif
</div>
<div class="four wide column">
   <h4><i class="pie chart icon"></i>Market Segment</h4>
</div>
<div class="twelve wide column @if($errors->has('market_segments')) error @endif">
  <select id="market_segment-field" name="market_segments[]" class="ui fluid search selection dropdown" multiple=""/>
        @foreach( $market_segments as $market_segment )
          <option name="market_segment" value="{{$market_segment->id}}">{{$market_segment->market_segment_name}}</option>
        @endforeach
    </select>
      @if($errors->has("market_segments"))
       <span class="ui pointing red basic label">{{ $errors->first("market_segments") }}</span>
      @endif
</div>
<div class="four wide column">
   <h4><i class="play icon"></i>Start</h4>
</div>
<div class="twelve wide column @if($errors->has('start')) error @endif">
  <div class="ui fluid corner labeled input">
    <input type="text" id="start-field" name="start" class="ui input" value="{{ old("start") }}" placeholder="2016-05-01 00:00:00" readonly="true"/>
    <script type="text/javascript">
    $(function() {
        $('#start-field').daterangepicker({
            format: 'YYYY-MM-DD HH:mm:ss',
            startDate: '2016-01-01 09:00:00',
            timePicker: true,
            timePicker24Hour: true,
            drops: 'up',
            singleDatePicker: true,
            showDropdowns: true,
            timePickerIncrement: 5,
            timePickerSeconds: true,
            autoApply: true
          });
    });
    </script>
    <div class="ui corner label">
      <i class="asterisk icon"></i>
    </div>
  </div>
       @if($errors->has("start"))
        <span class="ui pointing red basic label">{{ $errors->first("start") }}</span>
       @endif
</div>
<div class="four wide column">
   <h4><i class="stop icon"></i>Stop</h4>
</div>
<div class="twelve wide column @if($errors->has('stop')) error @endif">
  <div class="ui fluid corner labeled input">
    <input type="text" id="stop-field" name="stop" class="ui input" value="{{ old("stop") }}" placeholder="2016-05-01 00:00:00" readonly="true"/>
    <script type="text/javascript">
    $(function() {
        $('#stop-field').daterangepicker({
            format: 'YYYY-MM-DD HH:mm:ss',
            startDate: '2016-12-31 17:00:00',
            timePicker: true,
            timePicker24Hour: true,
            drops: 'up',
            singleDatePicker: true,
            showDropdowns: true,
            timePickerIncrement: 5,
            timePickerSeconds: true,
            autoApply: true
          });
    });
    </script>
    <div class="ui corner label">
      <i class="asterisk icon"></i>
    </div>
  </div>
       @if($errors->has("stop"))
        <span class="ui pointing red basic label">{{ $errors->first("stop") }}</span>
       @endif
</div>
<div class="four wide column">
   <h4><i class="git square icon"></i>Repository</h4>
</div>
<div class="twelve wide column @if($errors->has('repository')) error @endif">
  <div class="ui fluid corner labeled input">
    <textarea class="ui input" id="repository-field" rows="2" name="repository" placeholder="project.git (must exist on dev web1 /var/www/clients/client0/web2/web/repo/)">{{ old("repository") }}</textarea>
    <div class="ui corner label">
      <i class="asterisk icon"></i>
    </div>
  </div>
       @if($errors->has("repository"))
        <span class="ui pointing red basic label">{{ $errors->first("repository") }}</span>
       @endif
</div>
```
##Other Fields (Edit)
```

<div class="four wide column">
  <h4><i class="external icon"></i>URL</h4>
</div>
<div class="twelve wide column @if($errors->has('url')) has-error @endif">
  <div class="ui fluid corner labeled input">
    <input type="text" id="url-field" name="url" class="ui input" value="{{ ${{classSingle}}->url }}" placeholder="https://"/>
    <div class="ui corner label">
      <i class="asterisk icon"></i>
    </div>
  </div>
     @if($errors->has("url"))
      <span class="ui pointing red basic label">{{ $errors->first("url") }}</span>
     @endif
</div>
<div class="four wide column">
   <h4><i class="folder icon"></i>Type</h4>
</div>
<div class="twelve wide column @if($errors->has('type')) has-error @endif">
  <select id="type-field" name="type" class="ui fluid search selection dropdown"/>
    @foreach ($types as $type)
      @if($type->id == ${{classSingle}}->type)
    <option name="type" value="{{$type->id}}" selected>{{$type->type_name}}</option>
      @else
    <option name="type" value="{{$type->id}}">{{$type->type_name}}</option>
      @endif
    @endforeach

  </select>
     @if($errors->has("type"))
      <span class="ui pointing red basic label">{{ $errors->first("type") }}</span>
     @endif
</div>
<div class="four wide column">
   <h4><i class="marker icon"></i>Status</h4>
</div>
<div class="twelve wide column @if($errors->has('status')) has-error @endif">
  <select id="status-field" name="status" class="ui fluid search selection dropdown"/>
      @foreach ($statuses as $status)
        @if($status->id == ${{classSingle}}->status)
      <option name="status" value="{{$status->id}}" selected>{{$status->status_name}}</option>
        @else
      <option name="status" value="{{$status->id}}">{{$status->status_name}}</option>
        @endif
      @endforeach

    </select>
     @if($errors->has("status"))
      <span class="ui pointing red basic label">{{ $errors->first("status") }}</span>
     @endif
</div>
  <div class="four wide column">
     <h4><i class="folder outline icon"></i>Product Group</h4>
  </div>
  <div class="twelve wide column @if($errors->has('product_group')) has-error @endif">
    <select id="product_group-field" name="product_group" class="ui fluid search selection dropdown"/>
        @foreach ($product_groups as $product_group)
          @if($product_group->id == ${{classSingle}}->product_group)
        <option name="product_group" value="{{$product_group->id}}" selected>{{$product_group->product_group_name}}</option>
          @else
        <option name="product_group" value="{{$product_group->id}}">{{$product_group->product_group_name}}</option>
          @endif
        @endforeach

      </select>
       @if($errors->has("product_group"))
        <span class="ui pointing red basic label">{{ $errors->first("product_group") }}</span>
       @endif
  </div>
  <div class="four wide column">
     <h4><i class="pie chart icon"></i>Market Segment</h4>
  </div>
  <div class="twelve wide column @if($errors->has('market_segments')) error @endif">
    <select id="market_segment-field" name="market_segments[]" class="ui fluid search selection dropdown" multiple=""/>
          @foreach( $market_segments as $market_segment )
            <option name="market_segment" value="{{$market_segment->id}}">{{$market_segment->market_segment_name}}</option>
          @endforeach
          @foreach (${{classSingle}}->market_segments as ${{classSingle}}_segment)
            <option name="market_segment" value="{{${{classSingle}}_segment->id}}" selected>{{${{classSingle}}_segment->market_segment_name}}</option>
          @endforeach
      </select>
        @if($errors->has("market_segments"))
         <span class="ui pointing red basic label">{{ $errors->first("market_segments") }}</span>
        @endif
  </div>
<div class="four wide column">
   <h4><i class="play icon"></i>Start</h4>
</div>
<div class="twelve wide column @if($errors->has('start')) has-error @endif">
  <div class="ui fluid corner labeled input">
    <input type="text" id="start-field" name="start" class="ui input" value="{{ ${{classSingle}}->start }}" placeholder="2016-05-01 00:00:00" readonly="true"/>
    <script type="text/javascript">
    $(function() {

        $('#start-field').daterangepicker({
            format: 'YYYY-MM-DD HH:mm:ss',
            timePicker: true,
            timePicker24Hour: true,
            drops: 'up',
            singleDatePicker: true,
            showDropdowns: true,
            timePickerIncrement: 5,
            timePickerSeconds: true,
            autoApply: true
          });
    });
    </script>
    <div class="ui corner label">
      <i class="asterisk icon"></i>
    </div>
  </div>
     @if($errors->has("start"))
      <span class="ui pointing red basic label">{{ $errors->first("start") }}</span>
     @endif
</div>
<div class="four wide column">
   <h4><i class="stop icon"></i>Stop</h4>
</div>
<div class="twelve wide column @if($errors->has('stop')) has-error @endif">
  <div class="ui fluid corner labeled input">
    <input type="text" id="stop-field" name="stop" class="ui input" value="{{ ${{classSingle}}->stop }}" placeholder="2016-05-01 00:00:00" readonly="true"/>
    <script type="text/javascript">
    $(function() {
        $('#stop-field').daterangepicker({
            format: 'YYYY-MM-DD HH:mm:ss',
            timePicker: true,
            timePicker24Hour: true,
            drops: 'up',
            singleDatePicker: true,
            showDropdowns: true,
            timePickerIncrement: 5,
            timePickerSeconds: true,
            autoApply: true
          });
    });
    </script>
    <div class="ui corner label">
      <i class="asterisk icon"></i>
    </div>
  </div>
     @if($errors->has("stop"))
      <span class="ui pointing red basic label">{{ $errors->first("stop") }}</span>
     @endif
</div>
<div class="four wide column">
   <h4><i class="git square icon"></i>Repository</h4>
</div>
<div class="twelve wide column @if($errors->has('repository')) has-error @endif">
  <div class="ui fluid corner labeled input">
    <textarea class="form-control" id="repository-field" rows="2" name="repository" placeholder="{{classSingle}}.git (must exist on dev web1 /var/www/clients/client0/web2/web/repo/)">{{ ${{classSingle}}->repository }}</textarea>
    <div class="ui corner label">
      <i class="asterisk icon"></i>
    </div>
  </div>
     @if($errors->has("repository"))
      <span class="ui pointing red basic label">{{ $errors->first("repository") }}</span>
     @endif
</div>
```
##Other Fields (Show)
```

<div class="four wide column">
  <h4><i class="checkered flag icon"></i>Complete?</h4>
</div>
<div class="twelve wide column">
   <div class="ui read-only checkbox">
     @if(${{classSingle}}->completed == 1)
     <input type="checkbox" name="completed" checked="">
     <label for="completed"></label>
     @else
     <input type="checkbox" name="completed">
     <label for="completed"></label>
     @endif
   </div>
   @if(${{classSingle}}->completed == 1)
   <div class="ui green label"><i class="flag icon"></i>Yes</div>
   @else
   <div class="ui red label"><i class="flag outline icon"></i>No</div>
   @endif
</div>
```
##(Index)
```
<a class="ui mini button pull-right" href="{{ route('{{prefix}}{{class}}.index') }}"><i class="hide icon"></i>View Inactive</a>

<button type="submit" class="ui mini basic negative button"><i class="erase icon"></i>Delete</button>
```
##(Menu)
```
<a class="item" href="{{ URL::to('/{{prefix}}{{class}}') }}"><i class="{{class}} icon"></i>{{Class}}</a>
```
