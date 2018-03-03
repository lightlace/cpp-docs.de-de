---
title: CRichEditDoc-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditDoc
- AFXRICH/CRichEditDoc
- AFXRICH/CRichEditDoc::CreateClientItem
- AFXRICH/CRichEditDoc::GetStreamFormat
- AFXRICH/CRichEditDoc::GetView
- AFXRICH/CRichEditDoc::m_bRTF
dev_langs:
- C++
helpviewer_keywords:
- CRichEditDoc [MFC], CreateClientItem
- CRichEditDoc [MFC], GetStreamFormat
- CRichEditDoc [MFC], GetView
- CRichEditDoc [MFC], m_bRTF
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c427dc034a37bf3b0686b0fd95e62c3b718fbaea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cricheditdoc-class"></a>CRichEditDoc-Klasse
Mit [CRichEditView](../../mfc/reference/cricheditview-class.md) und [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), stellt die Funktionalität des rich-Edit-Steuerelements im Kontext der MFC Dokument-Ansichtsarchitektur bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CRichEditDoc : public COleServerDoc  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRichEditDoc::CreateClientItem](#createclientitem)|Wird aufgerufen, um die Bereinigung des Dokuments durchführen.|  
|[CRichEditDoc::GetStreamFormat](#getstreamformat)|Gibt an, ob der Stream Eingabe und Ausgabe Formatierungsinformationen enthalten sollen.|  
|[CRichEditDoc::GetView](#getview)|Ruft den Zeilenindex [CRichEditView](../../mfc/reference/cricheditview-class.md) Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRichEditDoc::m_bRTF](#m_brtf)|Gibt an, ob Stream-e/a Formatierung werden sollen.|  
  
## <a name="remarks"></a>Hinweise  
 Ein "rich-Edit-Steuerelement" ist ein Fenster, in dem der Benutzer eingeben kann, und Bearbeiten von Text. Der Text kann Zeichen- und absatzformatierung zugewiesen werden und kann eingebettete OLE-Objekte enthalten. Rich-Edit-Steuerelemente bieten eine Programmierschnittstelle für die Formatierung von Text an. Komponenten der Benutzeroberfläche zum Formatierungsvorgänge für den Benutzer verfügbar machen muss jedoch eine Anwendung implementiert werden.  
  
 `CRichEditView`der Text und Formatierung Texteigenschaft beibehalten. `CRichEditDoc`verwaltet die Liste der Clientelemente, die in der Ansicht sind. `CRichEditCntrItem`OLE-Clientelemente erläutert Container-Seite.  
  
 Diese allgemeinen Windows-Steuerelements (und somit die [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) und verwandte Klassen) ist verfügbar nur für Programme, die unter Windows 95-und Windows 98 und Windows NT, Version 3.51 und höher.  
  
 Ein Beispiel der Verwendung von einem rich-Edit-Dokument in einer MFC-Anwendung finden Sie unter der [WORDPAD](../../visual-cpp-samples.md) beispielanwendung.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)  
  
 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md)  
  
 `CRichEditDoc`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrich.h  
  
##  <a name="createclientitem"></a>CRichEditDoc::CreateClientItem  
 Mit dieser Funktion wird zum Erstellen einer `CRichEditCntrItem` -Objekt und zu diesem Dokument hinzufügen.  
  
```  
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;  
```  
  
### <a name="parameters"></a>Parameter  
 *preo*  
 Zeiger auf eine [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) Struktur der OLE-Element beschrieben wird. Die neue `CRichEditCntrItem` -Objekt erstellt wird, um diese OLE-Element. Wenn *Preo* ist **NULL**, das neue Clientelement ist leer.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf ein neues [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) Objekt, das zu diesem Dokument hinzugefügt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion führt keine OLE-Initialisierung.  
  
 Weitere Informationen finden Sie unter der [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) Struktur im Windows SDK.  
  
##  <a name="getstreamformat"></a>CRichEditDoc::GetStreamFormat  
 Rufen Sie diese Funktion, um zu bestimmen, die Text-Format für den Inhalt des rich-Edit streaming.  
  
```  
int GetStreamFormat() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der folgenden Flags:  
  
- `SF_TEXT`Gibt an, dass das rich-Edit-Steuerelement Formatierungsinformationen nicht verwaltet.  
  
- `SF_RTF`Gibt an, dass das rich-Edit-Steuerelement Formatierungsinformationen verwaltet.  
  
### <a name="remarks"></a>Hinweise  
 Der zurückgegebene Wert basiert auf der [M_bRTF](#m_brtf) -Datenmember. Diese Funktion gibt `SF_RTF` Wenn `m_bRTF` ist **"true"**ist, andernfalls `SF_TEXT`.  
  
##  <a name="getview"></a>CRichEditDoc::GetView  
 Rufen Sie diese Funktion den Zugriff auf die [CRichEditView](../../mfc/reference/cricheditview-class.md) Objekt zugeordnete `CRichEditDoc` Objekt.  
  
```  
virtual CRichEditView* GetView() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf die `CRichEditView` Objekt, das mit dem Dokument zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Der Text und Formatierung Informationen sind in enthalten die `CRichEditView` Objekt. Die `CRichEditDoc` -Objekt verwaltet die OLE-Elemente für die Serialisierung. Es darf nur eine `CRichEditView` für jede `CRichEditDoc`.  
  
##  <a name="m_brtf"></a>CRichEditDoc::m_bRTF  
 Wenn **"true"**, gibt an, dass [CRichEditCtrl::StreamIn](../../mfc/reference/cricheditctrl-class.md#streamin) und [CRichEditCtrl::StreamOut](../../mfc/reference/cricheditctrl-class.md#streamout) Absatz und Zeichenformaten Merkmale speichern soll.  
  
```  
BOOL m_bRTF;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel WORDPAD](../../visual-cpp-samples.md)   
 [COleServerDoc-Klasse](../../mfc/reference/coleserverdoc-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRichEditView-Klasse](../../mfc/reference/cricheditview-class.md)   
 [CRichEditCntrItem-Klasse](../../mfc/reference/cricheditcntritem-class.md)   
 [COleDocument-Klasse](../../mfc/reference/coledocument-class.md)   
 [CRichEditCtrl-Klasse](../../mfc/reference/cricheditctrl-class.md)
