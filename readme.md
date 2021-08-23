Kaynak kodlarýnýz var ise bu adýmlarý uygulayýn;

root/interfacemodule.py
Arat:
def MakeInterface(self):
Bul:
self.DRAGON_SOUL_IS_QUALIFIED = False
Deðiþtir:
self.DRAGON_SOUL_IS_QUALIFIED = True

game/src/char_dragonsoul.cpp
Arat:
CHARACTER::DragonSoul_IsQualified()
Bul:
return FindAffect(AFFECT_DRAGON_SOUL_QUALIFIED) != NULL;
Deðiþtir:
return True;

Daha önce görev ile açtýysanýz Navicat Player tablosuna gelip New Query butonuna basýn ve þunu yazýn;
Kod:
DELETE FROM `affect` WHERE `bType` = '540';

Kaynak kodlarýnýz yok ise bu adýmlarý uygulayýn;

simya_gorevsiz.quest:
quest dss_no_req begin
    state start begin
        when login with not ds.is_qualified() begin
            ds.give_qualification()
        end
    end
end