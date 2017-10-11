---
title: CD2DBrushProperties-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CommonInit
dev_langs:
- C++
helpviewer_keywords:
- CD2DBrushProperties [MFC], CD2DBrushProperties
- CD2DBrushProperties [MFC], CommonInit
ms.assetid: c77d717f-0a16-4d74-b2ce-0ae1766ed6f9
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: ce10f805968b31f0d3a832891c1e0e378277b626
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="cd2dbrushproperties-class"></a>CD2DBrushProperties-Klasse
Ein Wrapper für `D2D1_BRUSH_PROPERTIES`.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DBrushProperties : public D2D1_BRUSH_PROPERTIES;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DBrushProperties::CD2DBrushProperties](#cd2dbrushproperties)|Überladen. Erstellt eine `CD2D_BRUSH_PROPERTIES` Struktur|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DBrushProperties::CommonInit](#commoninit)|Initialisiert das Objekt|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `D2D1_BRUSH_PROPERTIES`  
  
 `CD2DBrushProperties`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="cd2dbrushproperties"></a>CD2DBrushProperties::CD2DBrushProperties  
 Erstellt eine CD2D_BRUSH_PROPERTIES-Struktur  
  
```  
CD2DBrushProperties();  
CD2DBrushProperties(FLOAT _opacity);

 
CD2DBrushProperties(
    D2D1_MATRIX_3X2_F _transform,  
    FLOAT _opacity = 1.);
```  
  
### <a name="parameters"></a>Parameter  
 `_opacity`  
 Die Basis Deckkraft des Pinsels. Der Standardwert ist 1,0.  
  
 `_transform`  
 Die Transformation, die auf den Pinsel angewendet  
  
##  <a name="commoninit"></a>CD2DBrushProperties::CommonInit  
 Initialisiert das Objekt  
  
```  
void CommonInit();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

