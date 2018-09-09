
## Ecshop 2.x 存在SQLi

### 利用链路：
user.php -> cls_template.php function dispaly -> cls_template.php function insert_mod -> function insert_*

### 缺陷代码：
```
user.php
num:302
if (empty($back_act))
    {
        if (empty($back_act) && isset($GLOBALS['_SERVER']['HTTP_REFERER']))
        {
            $back_act = strpos($GLOBALS['_SERVER']['HTTP_REFERER'], 'user.php') ? './index.php' : $GLOBALS['_SERVER']['HTTP_REFERER'];
        }
        ···
    }
···
    $smarty->assign('back_act', $back_act);
    $smarty->display('user_passport.dwt');
}
```

```
cls_template.php function dispaly()
···
foreach ($k AS $key => $val)
            {
                if (($key % 2) == 1)
                {
                    $k[$key] = $this->insert_mod($val);
                }
            }
            $out = implode('', $k);
···
```
cls_template.php
function insert_mod($name) // 处理动态内容
    {
        list($fun, $para) = explode('|', $name);
        $para = unserialize($para);
        $fun = 'insert_' . $fun;

        return $fun($para);
    }
```
