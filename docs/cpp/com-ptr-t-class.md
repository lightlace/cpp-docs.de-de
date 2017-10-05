---
title: _com_ptr_t-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t
dev_langs:
- C++
helpviewer_keywords:
- _com_ptr_t class
ms.assetid: 3753a8a0-03d4-4cfd-8a9a-74872ea53971
caps.latest.revision: 8
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
ms.openlocfilehash: 3979a33f095092c5cbaac91793c501e31304a6d4
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="comptrt-class"></a>_com_ptr_t-Klasse
**Microsoft-spezifisch**  
  
 Ein `_com_ptr_t`-Objekt kapselt einen COM-Schnittstellenzeiger und wird als "intelligenter" Zeiger bezeichnet. Diese Vorlagenklasse verwaltet die Zuordnung und durch Funktionsaufrufe an die **IUnknown** Memberfunktionen: `QueryInterface`, `AddRef`, und **Version**.  
  
 Ein intelligenter Zeiger in der Regel verweist die TypeDef-Definition bereitgestellt werden, indem Sie die **_COM_SMARTPTR_TYPEDEF** Makro. Dieses Makro erwartet einen Schnittstellennamen und die IID und deklariert eine Spezialisierung von `_com_ptr_t` mit dem Namen der Schnittstelle sowie dem Suffix `Ptr`. Zum Beispiel:  
  
```  
_COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));  
```  
  
 deklariert die `_com_ptr_t` Spezialisierung **IMyInterfacePtr**.  
  
 Eine Reihe von [funktionieren Vorlagen](../cpp/relational-function-templates.md), nicht Mitglieder dieser Vorlagenklasse-Klasse, unterstützen Vergleiche mit einem intelligenten Zeiger auf der rechten Seite des Vergleichsoperators.  
  
### <a name="construction"></a>Konstruktion  
  
|||  
|-|-|  
|[_com_ptr_t](../cpp/com-ptr-t-com-ptr-t.md)|Erstellt ein `_com_ptr_t`-Objekt.|  
  
### <a name="low-level-operations"></a>Vorgänge auf niedriger Stufe  
  
|||  
|-|-|  
|[AddRef](../cpp/com-ptr-t-addref.md)|Ruft die `AddRef` Memberfunktion von **IUnknown** für den gekapselten Schnittstellenzeiger auf.|  
|[Anfügen](../cpp/com-ptr-t-attach.md)|Kapselt einen unformatierten Schnittstellenzeiger vom Typ dieses intelligenten Zeigers.|  
|[CreateInstance](../cpp/com-ptr-t-createinstance.md)|Erstellt eine neue Instanz eines Objekts mit einem **CLSID** oder **ProgID**.|  
|[Trennen](../cpp/com-ptr-t-detach.md)|Extrahiert den gekapselten Schnittstellenzeiger und gibt ihn zurück.|  
|[GetActiveObject](../cpp/com-ptr-t-getactiveobject.md)|Fügt einer vorhandenen Instanz eines Objekts mit einem **CLSID** oder **ProgID**.|  
|[GetInterfacePtr](../cpp/com-ptr-t-getinterfaceptr.md)|Gibt den gekapselten Schnittstellenzeiger zurück.|  
|[QueryInterface](../cpp/com-ptr-t-queryinterface.md)|Ruft die `QueryInterface` Memberfunktion von **IUnknown** für den gekapselten Schnittstellenzeiger auf.|  
|[Version](../cpp/com-ptr-t-release.md)|Ruft die **Release** Memberfunktion von **IUnknown** für den gekapselten Schnittstellenzeiger auf.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator =](../cpp/com-ptr-t-operator-equal.md)|Weist einem vorhandenen `_com_ptr_t`-Objekt einen neuen Wert zu.|  
|[Operatoren ==,! =, \<, >, \<=, > =](../cpp/com-ptr-t-relational-operators.md)|Vergleichen Sie das intelligente Zeigerobjekt mit einem anderen intelligenten Zeiger, unformatierten Schnittstellenzeiger oder **NULL**.|  
|[Extraktoren](../cpp/com-ptr-t-extractors.md)|Extrahieren Sie den gekapselten COM-Schnittstellenzeiger.|  
  
**Ende Microsoft-spezifisch**  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** "comip.h"  
  
 **LIB:** "comsuppw.lib" oder "comsuppwd.lib" (siehe [/Zc: wchar_t (Wchar_t ist der systemeigene Typ)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) für Weitere Informationen)  
  
## <a name="see-also"></a>Siehe auch  
 [Compilerklassen für COM-Unterstützung](../cpp/compiler-com-support-classes.md)
