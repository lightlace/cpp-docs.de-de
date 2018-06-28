---
title: CHtmlEditDoc Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CHtmlEditDoc
- AFXHTML/CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::GetView
- AFXHTML/CHtmlEditDoc::IsModified
- AFXHTML/CHtmlEditDoc::OpenURL
dev_langs:
- C++
helpviewer_keywords:
- CHtmlEditDoc [MFC], CHtmlEditDoc
- CHtmlEditDoc [MFC], GetView
- CHtmlEditDoc [MFC], IsModified
- CHtmlEditDoc [MFC], OpenURL
ms.assetid: b2cca61f-e5d6-4099-b0d1-46bf85f0bd64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 86d8cf9b3011865fac58515fb3429a363dd5946f
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038958"
---
# <a name="chtmleditdoc-class"></a>CHtmlEditDoc-Klasse
Mit [CHtmlEditView](../../mfc/reference/chtmleditview-class.md), stellt die Funktionalität der WebBrowser-Bearbeitungsplattform im Rahmen der MFC-Dokument-/ Ansichtsarchitektur bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class AFX_NOVTABLE CHtmlEditDoc : public CDocument  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHtmlEditDoc::CHtmlEditDoc](#chtmleditdoc)|Erstellt ein `CHtmlEditDoc`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHtmlEditDoc::GetView](#getview)|Ruft die `CHtmlEditView` Objekt angefügt wird, zu diesem Dokument.|  
|[CHtmlEditDoc::IsModified](#ismodified)|Gibt zurück, ob das WebBrowser-Steuerelement für die zugeordnete Ansicht ein Dokuments enthält, das vom Benutzer geändert wurde.|  
|[CHtmlEditDoc::OpenURL](#openurl)|Öffnet eine URL an.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 `CHtmlEditDoc`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxhtml.h  
  
##  <a name="chtmleditdoc"></a>  CHtmlEditDoc::CHtmlEditDoc  
 Erstellt eine **CHtmlEditDoc** Objekt.  
  
```  
CHtmlEditDoc();
```  
  
##  <a name="getview"></a>  CHtmlEditDoc::GetView  
 Ruft die [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) Objekt angefügt wird, zu diesem Dokument.  
  
```  
virtual CHtmlEditView* GetView() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf des Dokuments **CHtmlEditView** Objekt.  
  
##  <a name="ismodified"></a>  CHtmlEditDoc::IsModified  
 Gibt zurück, ob das WebBrowser-Steuerelement für die zugeordnete Ansicht ein Dokuments enthält, das vom Benutzer geändert wurde.  
  
```  
virtual BOOL IsModified();
```  
  
##  <a name="openurl"></a>  CHtmlEditDoc::OpenURL  
 Öffnet eine URL an.  
  
```  
virtual BOOL OpenURL(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszURL*  
 Die URL zu öffnen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg **"false"** bei einem Fehler.  
  
## <a name="see-also"></a>Siehe auch  
 [HTMLEdit-Beispiel](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)

