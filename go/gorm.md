gorm在这种代码下会产生错误：
```
var db *gorm.DB
func main(){
  db,err := gorm.Open()
  db.xxx
}
```
你必须这样做：
```
var db *gorm.DB
func main(){
  var err error
  db,err = gorm.Open()
}
```
原因暂时还不知道
