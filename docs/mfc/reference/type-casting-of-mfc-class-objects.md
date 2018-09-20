---
title: Typumwandlung von MFC-Klassenobjekten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- macros [MFC], type casting
- pointers [MFC], type casting
- type casts [MFC]
- casting types [MFC]
- macros [MFC], casting pointers
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f459f1cad1b863f0c96e9c885fd2c54831d6b6e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382439"
---
# <a name="type-casting-of-mfc-class-objects"></a>Typumwandlung von MFC-Klassenobjekten

Type Casting Makros bieten eine Möglichkeit, einen angegebenen Zeiger auf einen Zeiger umwandeln, die verweist auf ein Objekt der spezifische Klasse, mit oder ohne stellt sicher, dass die Umwandlung zulässig ist.

Die folgende Tabelle enthält den Typ umwandeln von MFC-Makros.

### <a name="macros-that-cast-pointers-to-mfc-class-objects"></a>Makros, die Umwandlung von Zeigern auf MFC-Klassenobjekten

|||
|-|-|
|[DYNAMIC_DOWNCAST](#dynamic_downcast)|Wandelt einen Zeiger auf einen Zeiger auf ein Objekt der Klasse beim Überprüfen, um festzustellen, ob die Umwandlung zulässig ist.|
|[STATIC_DOWNCAST](#static_downcast)|Wandelt einen Zeiger auf ein Objekt von einer Klasse in einen Zeiger eines entsprechenden Typs. In einem Debugbuild verursacht eine ASSERTION, wenn das Objekt kein "von" in den Zieltyp.|

##  <a name="dynamic_downcast"></a>  DYNAMIC_DOWNCAST

Bietet eine praktische Möglichkeit, einen Zeiger auf einen Zeiger auf ein Objekt der Klasse umgewandelt, beim Überprüfen, um festzustellen, ob die Umwandlung zulässig ist.

```
DYNAMIC_DOWNCAST(class, pointer)
```

### <a name="parameters"></a>Parameter

*class*<br/>
Der Name einer Klasse.

*Zeiger*<br/>
Ein Zeiger auf einen Zeiger auf ein Objekt vom Typ umgewandelt werden *Klasse*.

### <a name="remarks"></a>Hinweise

Das Makro umgewandelt wird die *Zeiger* Parameter, um einen Zeiger auf ein Objekt der *Klasse* Typ des Parameters.

Wenn das Objekt, das auf der Zeiger verweist, ist ein "von" die bezeichnete Klasse das Makro gibt den entsprechenden Zeiger. Wenn es sich nicht um eine Umwandlung zulässig ist, gibt das Makro NULL zurück.

##  <a name="static_downcast"></a>  STATIC_DOWNCAST

Umwandlungen *Pobject* in einen Zeiger auf eine *Class_name* Objekt.

```
STATIC_DOWNCAST(class_name, pobject)
```

### <a name="parameters"></a>Parameter

*CLASS_NAME*<br/>
Der Name der Klasse dessen Typ umgewandelt wird.

*pObject*<br/>
Der Zeiger auf einen Zeiger auf umgewandelt werden eine *Class_name* Objekt.

### <a name="remarks"></a>Hinweise

*pObject* muss NULL sein, oder zeigen Sie auf ein Objekt einer Klasse, die direkt abgeleitet ist, oder indirekt von *Class_name*. In Builds Ihrer Anwendung mit der _DEBUG-Präprozessorsymbol definiert, wird das Makro bestätigen, wenn *Pobject* ist nicht NULL ist, oder zeigt auf ein Objekt, das nicht ist ein "von" der Klasse, die im angegebenen die *Class_name*Parameter (finden Sie unter [CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof)). In nicht- **_DEBUG** Builds, das Makro führt die Umwandlung ohne den Typ zu überprüfen.

Die Klasse, die im angegebenen die *Class_name* Parameter abgeleitet werden muss `CObject` verwenden müssen, die DECLARE_DYNAMIC und IMPLEMENT_DYNAMIC, dem DECLARE_DYNCREATE und IMPLEMENT_DYNCREATE, oder die DECLARE_SERIAL und IMPLEMENT_ SERIELLE Makros, wie in diesem Artikel erläutert [CObject-Klasse: Ableiten einer Klasse von CObject](../../mfc/deriving-a-class-from-cobject.md).

Sie können einen Zeiger auf z. B. eine Typumwandlung `CMyDoc`namens `pMyDoc`, in einen Zeiger auf `CDocument` mit folgendem Ausdruck:

[!code-cpp[NVC_MFCDocView#197](../../mfc/codesnippet/cpp/type-casting-of-mfc-class-objects_1.cpp)]

Wenn `pMyDoc` verweist nicht auf ein Objekt, das direkt oder indirekt von abgeleiteten `CDocument`, das Makro implementiert.

## <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
