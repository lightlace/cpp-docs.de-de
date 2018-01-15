---
title: Typumwandlung von MFC-Klassenobjekten | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros.classes
dev_langs: C++
helpviewer_keywords:
- macros [MFC], type casting
- pointers [MFC], type casting
- type casts [MFC]
- casting types [MFC]
- macros [MFC], casting pointers
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1fc887ad855b00b525c74b66bfc70f2adb3312e3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="type-casting-of-mfc-class-objects"></a>Typumwandlung von MFC-Klassenobjekten
Typ umwandeln Makros bieten eine Möglichkeit, das einen angegebenen Zeiger auf einen Zeiger umgewandelt, der auf ein Objekt der spezifische Klasse, mit oder ohne stellt sicher, dass die Umwandlung zulässig ist.  
  
 Die folgende Tabelle enthält den Typ umwandeln von MFC-Makros.  
  
### <a name="macros-that-cast-pointers-to-mfc-class-objects"></a>Makros, die Zeiger auf MFC-Klassenobjekten umgewandelt.  
  
|||  
|-|-|  
|[DYNAMIC_DOWNCAST](#dynamic_downcast)|Wandelt einen Zeiger auf einen Zeiger auf ein Klassenobjekt während des Überprüfens, um festzustellen, ob die Umwandlung zulässig ist.|  
|[STATIC_DOWNCAST](#static_downcast)|Wandelt einen Zeiger auf ein Objekt von einer Klasse in einen Zeiger, der einen zugehörigen Typ. In einem Debugbuild bewirkt, dass ein **ASSERT** ist das Objekt keine "Art von" in den Zieltyp.|  
  
##  <a name="dynamic_downcast"></a>DYNAMIC_DOWNCAST  
 Bietet eine praktische Möglichkeit zum Umwandeln von eines Zeigers auf einen Zeiger auf ein Klassenobjekt während des Überprüfens, um festzustellen, ob die Umwandlung zulässig ist.  
  
```   
DYNAMIC_DOWNCAST(class, pointer)  
```  
  
### <a name="parameters"></a>Parameter  
 `class`  
 Der Name einer Klasse.  
  
 `pointer`  
 Ein Zeiger auf einen Zeiger auf ein Objekt vom Typ umgewandelt werden `class`.  
  
### <a name="remarks"></a>Hinweise  
 Das Makro umgewandelt wird die `pointer` Parameter in einen Zeiger auf ein Objekt von der `class` Parametertyps.  
  
 Ist das Objekt, der vom Zeiger auf eine "Art von" die bezeichnete Klasse das Makro gibt den entsprechenden Zeiger. Wenn es sich nicht um eine Umwandlung zulässig ist, wird das Makro gibt **NULL**.  
  
##  <a name="static_downcast"></a>STATIC_DOWNCAST  
 Umwandlungen *Pobject* in einen Zeiger auf eine *Class_name* Objekt.  
  
```   
STATIC_DOWNCAST(class_name, pobject)   
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der Name der Klasse umgewandelt wird.  
  
 *pObject*  
 Der Zeiger in einen Zeiger auf umgewandelt werden ein *Class_name* Objekt.  
  
### <a name="remarks"></a>Hinweise  
 *pObject* muss entweder **NULL**, oder zeigen Sie auf ein Objekt, eine Klasse, die stammt direkt oder indirekt von *Class_name*. In Ihrer Anwendung mit der **_DEBUG** Präprozessorsymbol definiert, das Makro wird **ASSERT** Wenn *Pobject* nicht **NULL**, oder Wenn auf ein Objekt verwiesen wird, die keine "Art von" der Klasse, die im angegebenen der *Class_name* Parameter (finden Sie unter [CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof)). In nicht - **_DEBUG** Builds, das Makro führt die Umwandlung ohne Typ zu überprüfen.  
  
 Im angegebenen Klasse der *Class_name* Parameter muss abgeleitet sein `CObject` muss die `DECLARE_DYNAMIC` und `IMPLEMENT_DYNAMIC`, die `DECLARE_DYNCREATE` und `IMPLEMENT_DYNCREATE`, oder die `DECLARE_SERIAL` und `IMPLEMENT_SERIAL`Makros wie in diesem Artikel erläutert [CObject-Klasse: Ableiten einer Klasse von CObject](../../mfc/deriving-a-class-from-cobject.md).  
  
 Sie können einen Zeiger auf z. B. eine Typumwandlung `CMyDoc`namens `pMyDoc`, in einen Zeiger auf **CDocument** mit folgendem Ausdruck:  
  
 [!code-cpp[NVC_MFCDocView#197](../../mfc/codesnippet/cpp/type-casting-of-mfc-class-objects_1.cpp)]  
  
 Wenn `pMyDoc` verweist nicht auf ein Objekt direkt oder indirekt von abgeleiteten **CDocument**, wird das Makro **ASSERT**.  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
