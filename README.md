多文本框textarea实现高度自适应


#html： 
<div class="form-group">
    <label class="col-sm-3 control-label">回复：</label>
    <div class="col-sm-8">
        <textarea id="replyContent" name="replyContent" class="form-control textarea" contenteditable="true">[[*{replyContent}]]
        </textarea>
    </div>
</div>

#css：
<style type="text/css">
    .textarea {
        height: 100%;
        min-height: 20px;
        outline: 0;
        overflow: hidden;
    }
</style>


#js：
$('textarea').each(function (i) {
    this.style.height = 'auto';
    this.scrollTop = '0';
    this.style.height = this.scrollHeight + 'px';
    $("#"+ this.id).bind('input propertychange', function () {
        this.style.height = 'auto';
        this.scrollTop = '0';
        this.style.height = this.scrollHeight + 'px';
    })
})
