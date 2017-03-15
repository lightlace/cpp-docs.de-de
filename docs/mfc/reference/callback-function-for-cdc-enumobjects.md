---
title: "Rückruffunktion für CDC:: EnumObjects | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Callback Function for CDC::EnumObjects
dev_langs:
- C++
helpviewer_keywords:
- callback functions, for CDC::EnumObjects
ms.assetid: 380088b1-88a5-4fb4-bbb5-dd9e8386572b
caps.latest.revision: 10
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: e4b24b5f5333d5514b9fdf69d204bca5d7947d7a
ms.lasthandoff: 02/24/2017

---
# <a name="callback-function-for-cdcenumobjects"></a>Rückruffunktion für CDC::EnumObjects
Die *ObjectFunc* Name ist ein Platzhalter für den Namen der Anwendung bereitgestellte Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,  
    LPSTR* lpData);
```  
  
#### <a name="parameters"></a>Parameter  
 *lpszLogObject*  
 Verweist auf eine [LOGPEN](../../mfc/reference/logpen-structure.md) oder [LOGBRUSH](../../mfc/reference/logbrush-structure.md) -Datenstruktur, die Informationen über die logische Attribute des Objekts enthält.  
  
 `lpData`  
 Verweist auf die von der Anwendung bereitgestellten Daten übergeben, um die `EnumObjects` Funktion.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Callback-Funktion gibt eine `int`. Der Wert von diesem Return ist benutzerdefiniert. Wenn die Callback-Funktion gibt 0 zurück `EnumObjects` Enumeration vorzeitig beendet.  
  
## <a name="remarks"></a>Hinweise  
 Der Name muss exportiert werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC:: EnumObjects](../../mfc/reference/cdc-class.md#enumobjects)


