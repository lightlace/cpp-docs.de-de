---
title: Typumwandlung von MFC-Klassenobjekten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- macros, type casting
- pointers, type casting
- type casts
- casting types
- macros, casting pointers
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
caps.latest.revision: 15
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: f1ae094e7085017f03daab3f73323da13ab1be39
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="type-casting-of-mfc-class-objects"></a>Typumwandlung von MFC-Klassenobjekten
Typ umwandeln Makros bieten eine Möglichkeit, einen angegebenen Zeiger auf einen Zeiger umgewandelt, die auf ein Objekt einer bestimmten Klasse, mit oder ohne zu überprüfen, dass die Umwandlung zulässig ist.  
  
 Die folgende Tabelle enthält die Makros, die MFC-Typ umwandeln.  
  
### <a name="macros-that-cast-pointers-to-mfc-class-objects"></a>Makros, die Zeiger auf MFC-Klassenobjekten umgewandelt.  
  
|||  
|-|-|  
|[DYNAMIC_DOWNCAST](#dynamic_downcast)|Wandelt einen Zeiger auf einen Zeiger auf ein Objekt der Klasse beim Überprüfen, um festzustellen, ob die Umwandlung zulässig ist.|  
|[STATIC_DOWNCAST](#static_downcast)|Wandelt einen Zeiger auf ein Objekt aus einer Klasse in einen Zeiger eines zugehörigen Typs. In einem Debugbuild bewirkt, dass ein **ASSERT** ist das Objekt keine "Art von" den Zieltyp.|  
  
##  <a name="dynamic_downcast"></a>DYNAMIC_DOWNCAST  
 Bietet eine praktische Möglichkeit, einen Zeiger auf einen Zeiger auf ein Objekt der Klasse umgewandelt, beim Überprüfen, um festzustellen, ob die Umwandlung zulässig ist.  
  
```   
DYNAMIC_DOWNCAST(class, pointer)  
```  
  
### <a name="parameters"></a>Parameter  
 `class`  
 Der Name einer Klasse.  
  
 `pointer`  
 Ein Zeiger auf einen Zeiger auf ein Objekt vom Typ umgewandelt werden `class`.  
  
### <a name="remarks"></a>Hinweise  
 Das Makro umgewandelt werden die `pointer` Parameter, um einen Zeiger auf ein Objekt der `class` Typ des Parameters.  
  
 Wenn das Objekt auf der Zeiger verweist, ist eine "Art von" bezeichnete Klasse das Makro gibt den entsprechenden Zeiger zurück. Wenn es sich nicht um eine Umwandlung zulässig ist, wird das Makro gibt **NULL**.  
  
##  <a name="static_downcast"></a>STATIC_DOWNCAST  
 Umwandlungen *Pobject* in einen Zeiger auf eine *Class_name* Objekt.  
  
```   
STATIC_DOWNCAST(class_name, pobject)   
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der Name der Klasse umgewandelt wird.  
  
 *pObject*  
 Der Zeiger auf einen Zeiger auf umgewandelt werden ein *Class_name* Objekt.  
  
### <a name="remarks"></a>Hinweise  
 *pObject* muss entweder **NULL**, oder zeigen Sie auf ein Objekt einer Klasse, die direkt abgeleitet ist oder indirekt von *Class_name*. In Builds der Anwendung mit der **_DEBUG** Präprozessorsymbol definiert, das Makro wird **ASSERT** Wenn *Pobject* nicht **NULL**, oder wenn er auf ein Objekt verweist, die keine "Art von" im angegebenen Klasse der *Class_name* Parameter (finden Sie unter [CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof)). In nicht - **_DEBUG** Builds, das Makro führt die Umwandlung ohne Typ überprüft.  
  
 Im angegebenen Klasse der *Class_name* Parameter abgeleitet werden muss `CObject` und müssen die `DECLARE_DYNAMIC` und `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` und `IMPLEMENT_DYNCREATE`, oder die `DECLARE_SERIAL` und `IMPLEMENT_SERIAL` Makros, wie im Artikel erläutert [CObject-Klasse: Ableiten einer Klasse von CObject](../../mfc/deriving-a-class-from-cobject.md).  
  
 Sie können z. B. einen Zeiger auf umwandeln `CMyDoc`namens `pMyDoc`, in einen Zeiger auf **CDocument** mit folgendem Ausdruck:  
  
 [!code-cpp[NVC_MFCDocView&#197;](../../mfc/codesnippet/cpp/type-casting-of-mfc-class-objects_1.cpp)]  
  
 Wenn `pMyDoc` verweist nicht auf ein Objekt direkt oder indirekt von abgeleiteten **CDocument**, wird das Makro **ASSERT**.  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

