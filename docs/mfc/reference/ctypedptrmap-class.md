---
title: CTypedPtrMap-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTypedPtrMap
dev_langs:
- C++
helpviewer_keywords:
- type-safe collections
- template classes, CTypedPtrMap class
- maps
- CTypedPtrMap class
- pointer maps
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 919d751c6ffe4b10ffad047f1b6be832bf49a1af
ms.lasthandoff: 02/24/2017

---
# <a name="ctypedptrmap-class"></a>CTypedPtrMap-Klasse
Stellt einen typsicheren Wrapper für Objekte der Zeigerzuordnungsklassen `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`und `CMapStringToPtr`bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class BASE_CLASS, class KEY, class VALUE>  
class CTypedPtrMap : public BASE_CLASS  
```  
  
#### <a name="parameters"></a>Parameter  
 `BASE_CLASS`  
 Die Basisklasse der typisierten Zeigers Map-Klasse; muss eine Zeiger Map-Klasse ( `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`, oder `CMapStringToPtr`).  
  
 `KEY`  
 Die Klasse des Objekts, das als Schlüssel für die Zuordnung verwendet.  
  
 `VALUE`  
 Die Klasse des Objekts in der Zuordnung gespeichert.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTypedPtrMap::GetNextAssoc](#getnextassoc)|Ruft das nächste Element durchlaufen werden können.|  
|[CTypedPtrMap::Lookup](#lookup)|Gibt eine `KEY` basierend auf einer `VALUE`.|  
|[CTypedPtrMap::RemoveKey](#removekey)|Entfernt ein Element mit einem Schlüssel angegeben.|  
|[CTypedPtrMap::SetAt](#setat)|Fügt ein Element in der Zuordnung. ersetzt ein vorhandenes Element, wenn ein übereinstimmender Schlüssel gefunden wird.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTypedPtrMap::operator]](#operator_at)|Fügt ein Element in der Zuordnung.|  
  
## <a name="remarks"></a>Hinweise  
 Bei Verwendung `CTypedPtrMap`, die C++-Typprüfung-Funktion hilft Fehler aufgrund eines nicht übereinstimmenden Zeigertypen zu vermeiden.  
  
 Da alle `CTypedPtrMap` Funktionen sind Inline, die Verwendung dieser Vorlage erheblich wirkt sich nicht die Größe oder Geschwindigkeit Ihres Codes.  
  
 Weitere Informationen zur Verwendung von `CTypedPtrMap`, finden Sie in den Artikeln [Sammlungen](../../mfc/collections.md) und [Vorlagen basierende Klassen](../../mfc/template-based-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `BASE_CLASS`  
  
 `CTypedPtrMap`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtempl.h  
  
##  <a name="a-namegetnextassoca--ctypedptrmapgetnextassoc"></a><a name="getnextassoc"></a>CTypedPtrMap::GetNextAssoc  
 Ruft das Map-Element in `rNextPosition`, dann werden die `rNextPosition` zum Verweisen auf das nächste Element in der Zuordnung.  
  
```  
void GetNextAssoc(
    POSITION& rPosition,
    KEY& rKey,
    VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `rPosition`  
 Gibt einen Verweis auf eine **POSITION** von einem vorherigen zurückgegebene Wert `GetNextAssoc` oder `BASE_CLASS` **:: GetStartPosition** aufrufen.  
  
 *SCHLÜSSEL*  
 Der Vorlagenparameter, der den Schlüsseln der Zuordnung angibt.  
  
 `rKey`  
 Gibt den zurückgegebenen Schlüssel des Elements abgerufen.  
  
 *WERT*  
 Der Vorlagenparameter, die den Typ der Werte für die Zuordnung.  
  
 `rValue`  
 Gibt den zurückgegebenen Wert des Elements abgerufen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist besonders hilfreich für die Iteration durch alle Elemente in der Zuordnung. Beachten Sie, dass die Sequenz Position nicht unbedingt die Sequenz von Schlüssel-Wert identisch ist.  
  
 Wenn das abgerufene Element das letzte Element in der Zuordnung und dann der neue Wert der `rNextPosition` Wert **NULL**.  
  
 Diese Inline-Funktionsaufrufe `BASE_CLASS` **:: GetNextAssoc**.  
  
##  <a name="a-namelookupa--ctypedptrmaplookup"></a><a name="lookup"></a>CTypedPtrMap::Lookup  
 `Lookup`verwendet einen Hashalgorithmus schnell das Map-Element mit einem Schlüssel finden, die genau übereinstimmt.  
  
```  
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `BASE_CLASS`  
 Festlegen der Basisklasse der Klasse diese Zuordnung Vorlagenparameter.  
  
 `key`  
 Der Schlüssel des Elements, das gesucht werden sollen.  
  
 *WERT*  
 Der Vorlagenparameter, die den Typ der Werte in dieser Zuordnung gespeichert.  
  
 `rValue`  
 Gibt den zurückgegebenen Wert des Elements abgerufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Element gefunden wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Inline-Funktionsaufrufe `BASE_CLASS` **:: Lookup**.  
  
##  <a name="a-nameoperatorata--ctypedptrmapoperator--"></a><a name="operator_at"></a>CTypedPtrMap::operator]  
 Dieser Operator kann nur auf der linken Seite einer zuweisungsanweisung (ein l-Wert) verwendet werden.  
  
```  
VALUE& operator[ ](base_class ::base_arg_key key);
```  
  
### <a name="parameters"></a>Parameter  
 *WERT*  
 Der Vorlagenparameter, die den Typ der Werte in dieser Zuordnung gespeichert.  
  
 `BASE_CLASS`  
 Festlegen der Basisklasse der Klasse diese Zuordnung Vorlagenparameter.  
  
 `key`  
 Der Schlüssel des Elements, das gesucht oder in der Zuordnung erstellt werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn kein Map-Element mit dem angegebenen Schlüssel vorhanden ist, wird ein neues Element erstellt. Es gibt keine "rechts" (r) dieser Operator entspricht, da es besteht die Möglichkeit, die ein Schlüssel nicht in der Zuordnung gefunden werden kann. Verwenden der `Lookup` Member-Funktion für das Element abrufen.  
  
##  <a name="a-nameremovekeya--ctypedptrmapremovekey"></a><a name="removekey"></a>CTypedPtrMap::RemoveKey  
 Diese Memberfunktion ruft `BASE_CLASS` **:: RemoveKey**.  
  
```  
BOOL RemoveKey(KEY key);
```  
  
### <a name="parameters"></a>Parameter  
 *SCHLÜSSEL*  
 Der Vorlagenparameter, der den Schlüsseln der Zuordnung angibt.  
  
 `key`  
 Der Schlüssel für das Element entfernt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Eintrag gefunden und erfolgreich entfernt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Hinweise finden Sie unter [CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey).  
  
##  <a name="a-namesetata--ctypedptrmapsetat"></a><a name="setat"></a>CTypedPtrMap::SetAt  
 Diese Memberfunktion ruft `BASE_CLASS` **:: SetAt**.  
  
```  
void SetAt(KEY key, VALUE newValue);
```  
  
### <a name="parameters"></a>Parameter  
 *SCHLÜSSEL*  
 Der Vorlagenparameter, der den Schlüsseln der Zuordnung angibt.  
  
 `key`  
 Gibt den Schlüsselwert der NewValue an.  
  
 `newValue`  
 Gibt den Zeiger des Objekts, das der Wert des neuen Elements an.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Hinweise finden Sie unter [CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel COLLECT](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr-Klasse](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord-Klasse](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapWordToPtr-Klasse](../../mfc/reference/cmapwordtoptr-class.md)   
 [CMapStringToPtr-Klasse](../../mfc/reference/cmapstringtoptr-class.md)

