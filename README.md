# simya-penceresini-gorevsiz-acma

Elinizde Source dosyaları var ise şu adımları uygulayın;

> root/interfacemodule.py
>Arat:
```
def MakeInterface(self):
```
> Bul:
```
self.DRAGON_SOUL_IS_QUALIFIED = False
```
> Değiştir:
```
self.DRAGON_SOUL_IS_QUALIFIED = True
```

> game/src/char_dragonsoul.cpp
Arat:
```
CHARACTER::DragonSoul_IsQualified()
```
> Bul:
```
return FindAffect(AFFECT_DRAGON_SOUL_QUALIFIED) != NULL;
```
> Değiştir:
```
return True;
```


> Daha önce görev ile açtıysanız Navicat Player tablosuna gelip New Query butonuna basın ve şunu yazın;
```
DELETE FROM `affect` WHERE `bType` = '540';
```


> Elinizde Source dosyaları yok ise buradaki questi kullanın;

> simya_gorevsiz.quest:
```
quest dss_no_req begin
    state start begin
        when login with not ds.is_qualified() begin
            ds.give_qualification()
        end
    end
end
```
