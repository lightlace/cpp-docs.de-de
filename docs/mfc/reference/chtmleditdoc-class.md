---
title: Klasse CHtmlEditDoc | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CHtmlEditDoc class
ms.assetid: b2cca61f-e5d6-4099-b0d1-46bf85f0bd64
caps.latest.revision: 24
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 1d9651c5009fd8f4c742c6b9bf08e32bd67c7d30
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="chtmleditdoc-class"></a>CHtmlEditDoc-Klasse
Mit [CHtmlEditView](../../mfc/reference/chtmleditview-class.md), stellt die Funktionalität der WebBrowser-Bearbeitungsplattform im Rahmen der Dokument-/ Ansichtarchitektur von MFC bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class AFX_NOVTABLE CHtmlEditDoc : public CDocument  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHtmlEditDoc::CHtmlEditDoc](#chtmleditdoc)|Erstellt ein `CHtmlEditDoc`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHtmlEditDoc::GetView](#getview)|Ruft die `CHtmlEditView` Objekt an diesem Dokument angefügt.|  
|[CHtmlEditDoc::IsModified](#ismodified)|Gibt zurück, ob die zugeordnete Ansicht WebBrowser-Steuerelement ein Dokument enthält, die vom Benutzer geändert wurde.|  
|[CHtmlEditDoc::OpenURL](#openurl)|Öffnet eine URL an.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 `CHtmlEditDoc`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxhtml.h  
  
##  <a name="chtmleditdoc"></a>CHtmlEditDoc::CHtmlEditDoc  
 Erstellt eine **CHtmlEditDoc** Objekt.  
  
```  
CHtmlEditDoc();
```  
  
##  <a name="getview"></a>CHtmlEditDoc::GetView  
 Ruft die [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) Objekt an diesem Dokument angefügt.  
  
```  
virtual CHtmlEditView* GetView() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf des Dokuments **CHtmlEditView** Objekt.  
  
##  <a name="ismodified"></a>CHtmlEditDoc::IsModified  
 Gibt zurück, ob die zugeordnete Ansicht WebBrowser-Steuerelement ein Dokument enthält, die vom Benutzer geändert wurde.  
  
```  
virtual BOOL IsModified();
```  
  
##  <a name="openurl"></a>CHtmlEditDoc::OpenURL  
 Öffnet eine URL an.  
  
```  
virtual BOOL OpenURL(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszURL`  
 Die URL zu öffnen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
## <a name="see-also"></a>Siehe auch  
 [HTMLEdit-Beispiel](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)


