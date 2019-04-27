---
title: _com_ptr_t-Klasse
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t
helpviewer_keywords:
- _com_ptr_t class
ms.assetid: 3753a8a0-03d4-4cfd-8a9a-74872ea53971
ms.openlocfilehash: ce19dbc5f55460bb4bdbdee17f4fbbbcc8c6fd60
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154902"
---
# <a name="comptrt-class"></a>_com_ptr_t-Klasse

**Microsoft-spezifisch**

Ein **_com_ptr_t** -Objekt kapselt einen COM-Schnittstellenzeiger und wird als "intelligenten" Zeiger bezeichnet. Diese Vorlagenklasse verwaltet Ressourcen belegen und freigeben, die durch Funktionsaufrufe an die `IUnknown` Memberfunktionen: `QueryInterface`, `AddRef`, und `Release`.

Ein intelligenter Zeiger wird in der Regel durch die Typedef-Definition bereitgestellt werden, durch das Makro _COM_SMARTPTR_TYPEDEF verwiesen. Dieses Makro nimmt einen Schnittstellennamen und die IID und deklariert eine Spezialisierung von **_com_ptr_t** mit dem Namen der Schnittstelle sowie dem Suffix `Ptr`. Zum Beispiel:

```cpp
_COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));
```

deklariert die **_com_ptr_t** Spezialisierung `IMyInterfacePtr`.

Eine Reihe von [Vorlagen funktionieren](../cpp/relational-function-templates.md), nicht Mitglieder dieser Vorlagenklasse-Klasse, unterstützen Vergleiche mit einem intelligenten Zeiger auf der rechten Seite des Vergleichsoperators.

### <a name="construction"></a>Konstruktion

|||
|-|-|
|[_com_ptr_t](../cpp/com-ptr-t-com-ptr-t.md)|Erstellt eine **_com_ptr_t** Objekt.|

### <a name="low-level-operations"></a>Vorgänge auf niedriger Stufe

|||
|-|-|
|[AddRef](../cpp/com-ptr-t-addref.md)|Ruft die `AddRef` Memberfunktion `IUnknown` für den gekapselten Schnittstellenzeiger auf.|
|[Anfügen](../cpp/com-ptr-t-attach.md)|Kapselt einen unformatierten Schnittstellenzeiger vom Typ dieses intelligenten Zeigers.|
|[CreateInstance](../cpp/com-ptr-t-createinstance.md)|Erstellt eine neue Instanz eines angegebenen Objekts an eine `CLSID` oder `ProgID`.|
|[Trennen](../cpp/com-ptr-t-detach.md)|Extrahiert den gekapselten Schnittstellenzeiger und gibt ihn zurück.|
|[GetActiveObject](../cpp/com-ptr-t-getactiveobject.md)|Fügt zu einer vorhandenen Instanz eines angegebenen Objekts an eine `CLSID` oder `ProgID`.|
|[GetInterfacePtr](../cpp/com-ptr-t-getinterfaceptr.md)|Gibt den gekapselten Schnittstellenzeiger zurück.|
|[QueryInterface](../cpp/com-ptr-t-queryinterface.md)|Ruft die `QueryInterface` Memberfunktion `IUnknown` für den gekapselten Schnittstellenzeiger auf.|
|[Version](../cpp/com-ptr-t-release.md)|Ruft die `Release` Memberfunktion `IUnknown` für den gekapselten Schnittstellenzeiger auf.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator =](../cpp/com-ptr-t-operator-equal.md)|Weist einen neuen Wert zu einem vorhandenen **_com_ptr_t** Objekt.|
|[operators ==, !=, \<, >, \<=, >=](../cpp/com-ptr-t-relational-operators.md)|Vergleichen Sie das intelligente Zeigerobjekt mit einem anderen intelligenten Zeiger, unformatierten Schnittstellenzeiger oder NULL.|
|[Extraktoren](../cpp/com-ptr-t-extractors.md)|Extrahieren Sie den gekapselten COM-Schnittstellenzeiger.|

**Ende Microsoft-spezifisch**

## <a name="requirements"></a>Anforderungen

**Header:** \<comip.h>

**LIB:** comsuppw.lib oder comsuppwd.lib (finden Sie unter [/Zc: wchar_t (Wchar_t ist der systemeigene Typ)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) Informationen)

## <a name="see-also"></a>Siehe auch

[Compilerklassen für COM-Unterstützung](../cpp/compiler-com-support-classes.md)