//1. 我们在数据库操作的时候，比如 dao 层中当遇到一个 sql.ErrNoRows 的时候，是否应该 Wrap 这个 error，抛给上层。为什么，应该怎么做请写出代码？
//答：一般dao层错误都是要往上抛的，但sql.ErrNoRows不用，它只是用来返回QueryRows()的结果，不需要抛到上层，但需要特殊处理一下。

var name string
err = db.QueryRow("select name from users where id = ?", 1).Scan(&name)
if err != nil {
    if err == sql.ErrNoRows {
        //没有行，但也没有错误发生
    } else {
        log.Fatal(err)
    }
}
fmt.Println(name)
