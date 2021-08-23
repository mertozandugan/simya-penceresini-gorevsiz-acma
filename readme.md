Kaynak kodlar�n�z var ise bu ad�mlar� uygulay�n;

root/interfacemodule.py
Arat:
def MakeInterface(self):
Bul:
self.DRAGON_SOUL_IS_QUALIFIED = False
De�i�tir:
self.DRAGON_SOUL_IS_QUALIFIED = True

game/src/char_dragonsoul.cpp
Arat:
CHARACTER::DragonSoul_IsQualified()
Bul:
return FindAffect(AFFECT_DRAGON_SOUL_QUALIFIED) != NULL;
De�i�tir:
return True;

Daha �nce g�rev ile a�t�ysan�z Navicat Player tablosuna gelip New Query butonuna bas�n ve �unu yaz�n;
Kod:
DELETE FROM `affect` WHERE `bType` = '540';

Kaynak kodlar�n�z yok ise bu ad�mlar� uygulay�n;

simya_gorevsiz.quest:
quest dss_no_req begin
    state start begin
        when login with not ds.is_qualified() begin
            ds.give_qualification()
        end
    end
end