---
title: CTypedPtrMap-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTypedPtrMap
- AFXTEMPL/CTypedPtrMap
- AFXTEMPL/CTypedPtrMap::GetNextAssoc
- AFXTEMPL/CTypedPtrMap::Lookup
- AFXTEMPL/CTypedPtrMap::RemoveKey
- AFXTEMPL/CTypedPtrMap::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CTypedPtrMap [MFC], GetNextAssoc
- CTypedPtrMap [MFC], Lookup
- CTypedPtrMap [MFC], RemoveKey
- CTypedPtrMap [MFC], SetAt
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9056fc73e2718b2a21936c39e630f4d4fddf1eed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
 Die Basisklasse der typisierten Zeiger Map-Klasse; muss eine Zeiger Map-Klasse ( `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`, oder `CMapStringToPtr`).  
  
 `KEY`  
 Die Klasse des Objekts, das als Schlüssel für die Zuordnung verwendet.  
  
 `VALUE`  
 Die Klasse des Objekts in der Zuordnung gespeichert.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTypedPtrMap::GetNextAssoc](#getnextassoc)|Ruft das nächste Element für die Iteration an.|  
|[CTypedPtrMap::Lookup](#lookup)|Gibt eine `KEY` basierend auf einer `VALUE`.|  
|[CTypedPtrMap::RemoveKey](#removekey)|Entfernt ein Element mit einem Schlüssel angegeben.|  
|[CTypedPtrMap::SetAt](#setat)|Fügt ein Element in der Zuordnung; ersetzt ein vorhandenes Element, wenn ein übereinstimmender Schlüssel gefunden wird.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTypedPtrMap::operator]](#operator_at)|Fügt ein Element in der Zuordnung.|  
  
## <a name="remarks"></a>Hinweise  
 Bei Verwendung von `CTypedPtrMap`, Typprüfung-Funktion für C++ hilft Fehler aufgrund nicht übereinstimmender Zeigertypen zu vermeiden.  
  
 Da alle `CTypedPtrMap` Funktionen sind Inline, die Verwendung dieser Vorlage erheblich wirkt sich nicht die Größe oder Geschwindigkeit Ihres Codes.  
  
 Weitere Informationen zur Verwendung von `CTypedPtrMap`, finden Sie in den Artikeln [Sammlungen](../../mfc/collections.md) und [Template-basierten Klassen](../../mfc/template-based-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `BASE_CLASS`  
  
 `CTypedPtrMap`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtempl.h  
  
##  <a name="getnextassoc"></a>CTypedPtrMap::GetNextAssoc  
 Ruft das kartenelement auf `rNextPosition`, aktualisiert dann `rNextPosition` zum Verweisen auf das nächste Element in der Zuordnung.  
  
```  
void GetNextAssoc(
    POSITION& rPosition,
    KEY& rKey,
    VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `rPosition`  
 Gibt einen Verweis auf eine **POSITION** von einem vorherigen zurückgegebene Wert `GetNextAssoc` oder `BASE_CLASS` **:: GetStartPosition** aufrufen.  
  
 *KEY*  
 Der Vorlagenparameter, den Typ der Schlüssel der Zuordnung angibt.  
  
 `rKey`  
 Gibt an, der zurückgegebene Schlüssel des Elements abgerufen.  
  
 *WERT*  
 Vorlagenparameter, den Typ der Werte der Zuordnung angibt.  
  
 `rValue`  
 Gibt den zurückgegebenen Wert des abgerufenen Elements.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist besonders hilfreich für die Iteration durch alle Elemente in der Zuordnung. Beachten Sie, dass die Sequenz Position nicht notwendigerweise die Sequenz von Schlüssel-Wert identisch ist.  
  
 Wenn das abgerufene Element das letzte Element in der Zuordnung klicken Sie dann der neue Wert des `rNextPosition` festgelegt ist, um **NULL**.  
  
 Diese Inlinefunktion ruft `BASE_CLASS` **:: GetNextAssoc**.  
  
##  <a name="lookup"></a>CTypedPtrMap::Lookup  
 `Lookup`verwendet einen Hashalgorithmus auf um das kartenelement schnell mit einem Schlüssel zu suchen, die genau übereinstimmt.  
  
```  
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `BASE_CLASS`  
 Der Vorlagenparameter ist die Basisklasse der Klasse für diese Zuordnung angeben.  
  
 `key`  
 Der Schlüssel des Elements, das gesucht werden sollen.  
  
 *WERT*  
 Der Vorlagenparameter Angabe des Typs der Werte in dieser Zuordnung gespeichert.  
  
 `rValue`  
 Gibt den zurückgegebenen Wert des abgerufenen Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Element gefunden wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Inlinefunktion ruft `BASE_CLASS` **:: Lookup**.  
  
##  <a name="operator_at"></a>CTypedPtrMap::operator]  
 Dieser Operator kann nur auf der linken Seite einer zuweisungsanweisung (ein l-Wert) verwendet werden.  
  
```  
VALUE& operator[ ](base_class ::base_arg_key key);
```  
  
### <a name="parameters"></a>Parameter  
 *WERT*  
 Der Vorlagenparameter Angabe des Typs der Werte in dieser Zuordnung gespeichert.  
  
 `BASE_CLASS`  
 Der Vorlagenparameter ist die Basisklasse der Klasse für diese Zuordnung angeben.  
  
 `key`  
 Der Schlüssel des Elements, das gesucht werden oder in der Zuordnung erstellt werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn kein Map-Element mit dem angegebenen Schlüssel vorhanden ist, wird ein neues Element erstellt. Es gibt keine "rechts" (r), die dieser Operator entspricht, da es besteht die Möglichkeit, die ein Schlüssel in der Zuordnung nicht gefunden werden kann. Verwenden der `Lookup` Member-Funktion für den Abruf von Listenelementen.  
  
##  <a name="removekey"></a>CTypedPtrMap::RemoveKey  
 Diese Memberfunktion ruft `BASE_CLASS` **:: RemoveKey**.  
  
```  
BOOL RemoveKey(KEY key);
```  
  
### <a name="parameters"></a>Parameter  
 *KEY*  
 Der Vorlagenparameter, den Typ der Schlüssel der Zuordnung angibt.  
  
 `key`  
 Schlüssel für das Element entfernt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Eintrag gefunden und erfolgreich entfernt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ausführlichere Hinweise finden Sie unter [CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey).  
  
##  <a name="setat"></a>CTypedPtrMap::SetAt  
 Diese Memberfunktion ruft `BASE_CLASS` **:: SetAt**.  
  
```  
void SetAt(KEY key, VALUE newValue);
```  
  
### <a name="parameters"></a>Parameter  
 *KEY*  
 Der Vorlagenparameter, den Typ der Schlüssel der Zuordnung angibt.  
  
 `key`  
 Gibt den Schlüsselwert, der die NewValue an.  
  
 `newValue`  
 Gibt die Objektzeiger, der den Wert des neuen Elements ist.  
  
### <a name="remarks"></a>Hinweise  
 Ausführlichere Hinweise finden Sie unter [CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel erfassen](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr-Klasse](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord-Klasse](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapWordToPtr-Klasse](../../mfc/reference/cmapwordtoptr-class.md)   
 [CMapStringToPtr-Klasse](../../mfc/reference/cmapstringtoptr-class.md)
