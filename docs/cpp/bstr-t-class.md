---
title: _bstr_t-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t
dev_langs:
- C++
helpviewer_keywords:
- BSTR object
- _bstr_t class
- BSTR object [C++], COM encapsulation
ms.assetid: 58841fef-fe21-4a84-aab9-780262b5201f
caps.latest.revision: 9
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: ce63f8243bc46d77116dbacdf82f821333cba785
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="bstrt-class"></a>_bstr_t-Klasse
**Microsoft-spezifisch**  
  
 Ein `_bstr_t` -Objekt kapselt die [BSTR-Datentyp](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228). Die Klasse verwaltet die Zuordnung und durch Funktionsaufrufe an **SysAllocString** und **SysFreeString** und andere `BSTR` APIs, falls erforderlich. Die `_bstr_t`-Klasse verwendet die Verweiszählung, um übermäßigen Mehraufwand zu vermeiden.  
  
### <a name="construction"></a>Konstruktion  
  
|||  
|-|-|  
|[_bstr_t](../cpp/bstr-t-bstr-t.md)|Erstellt ein `_bstr_t`-Objekt.|  
  
### <a name="operations"></a>Vorgänge  
  
|||  
|-|-|  
|[Zuweisen](../cpp/bstr-t-assign.md)|Kopiert ein `BSTR` in das `BSTR`, das von einem `_bstr_t` umschlossen wird.|  
|[Anfügen](../cpp/bstr-t-attach.md)|Verknüpft einen `_bstr_t`-Wrapper mit einem `BSTR`.|  
|[copy](../cpp/bstr-t-copy.md)|Erstellt eine Kopie des gekapselten `BSTR`.|  
|[Trennen](../cpp/bstr-t-detach.md)|Gibt `BSTR` zurück, das von `_bstr_t` umschlossen ist, und trennt `BSTR` von `_bstr_t`.|  
|[GetAddress](../cpp/bstr-t-getaddress.md)|Zeigt auf den `BSTR`, der von einem `_bstr_t` umschlossen ist.|  
|[GetBSTR](../cpp/bstr-t-getbstr.md)|Zeigt auf den Anfang des `BSTR`, das vom `_bstr_t` umschlossen ist.|  
|[length](../cpp/bstr-t-length.md)|Gibt die Anzahl von Zeichen in `_bstr_t` zurück.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator =](../cpp/bstr-t-operator-equal.md)|Weist einem vorhandenen `_bstr_t`-Objekt einen neuen Wert zu.|  
|[Operator +=](../cpp/bstr-t-operator-add-equal-plus.md)|Fügt Zeichen an das Ende des `_bstr_t`-Objekts an.|  
|[Operator +](../cpp/bstr-t-operator-add-equal-plus.md)|Verkettet zwei Zeichenfolgen.|  
|[Operator !](../cpp/bstr-t-operator-logical-not.md)|Überprüft, ob das gekapselte `BSTR` ist ein **NULL** Zeichenfolge.|  
|[Operator ==,! =, \<, >, \<=, > =](../cpp/bstr-t-relational-operators.md)|Vergleicht zwei `_bstr_t`-Objekte.|  
|[Operator Wchar_t * &#124; Char\*](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md)|Extrahiert die Zeiger auf das gekapselten Unicode- oder Mehrbyte-`BSTR`-Objekt.|  
  
**Ende Microsoft-spezifisch**  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** comutil.h  
  
 **LIB:** "comsuppw.lib" oder "comsuppwd.lib" (siehe [/Zc: wchar_t (Wchar_t ist der systemeigene Typ)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) für Weitere Informationen)  
  
## <a name="see-also"></a>Siehe auch  
 [Compilerklassen für COM-Unterstützung](../cpp/compiler-com-support-classes.md)
