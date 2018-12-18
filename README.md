# Searchable Select

# How to use

```html
<select>
  <option value="Personalize">Personalize</option>
  <option value="BlackBerry">BlackBerry</option>
  <option value="device">device</option>
  <option value="with">with</option>
  <option value="entertainment">entertainment</option>
  <option value="and">and</option>
  <option value="social">social</option>
  <option value="networking">networking</option>
  <option value="apps">apps</option>
  <option value="or">or</option>
  <option value="apps">apps</option>
  <option value="that">that</option>
  <option value="will">will</option>
  <option value="boost">boost</option>
  <option value="your">your</option>
  <option value="productivity">productivity</option>
  <option value="Download">Download</option>
  <option value="or">or</option>
  <option value="buy">buy</option>
  <option value="apps">apps</option>
  <option value="from">from</option>
  <option value="Afbb">Afbb</option>
  <option value="Akademie">Akademie</option>
  <option value="Berlin">Berlin</option>
  <option value="reviews">reviews</option>
  <option value="by">by</option>
  <option value="real">real</option>
</select>
```

You need script like this:


```javascript
<script>
  $(function(){
    $('select').searchableSelect();
  });
</script>
```

引用自[完美解决searchableselect不支持change事件的方法](https://www.jianshu.com/p/0c530ee3a4e7)

```javascript
// 完美解决searchableselect不支持change事件的方法
selectItem: function(item){
      if(this.hasCurrentSelectedItem())
        this.currentSelectedItem.removeClass('selected');
 
      this.currentSelectedItem = item;
      item.addClass('selected');
 
      this.hoverItem(item);
 
      this.holder.text(item.text());
      var value = item.data('value');
      this.holder.data('value', value);
      this.element.val(value);
    
       //模拟select触发change事件
      this.element.trigger('change');       
      
      if(this.options.afterSelectItem){
        this.options.afterSelectItem.apply(this);
      }
    },

```

# Author

David Qin
