---
title: CMultiPageDHtmlDialog Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog
dev_langs:
- C++
helpviewer_keywords:
- CMultiPageDHtmlDialog [MFC], CMultiPageDHtmlDialog
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2be83e3791121bdea4d7f650f7d6801517df31ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373891"
---
# <a name="cmultipagedhtmldialog-class"></a>CMultiPageDHtmlDialog-Klasse
Ein mehrseitiges Dialogfeld zeigt mehrere HTML-Seiten sequenziell an und behandelt die Ereignisse jeder Seite.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMultiPageDHtmlDialog : public CDHtmlDialog  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMultiPageDHtmlDialog::CMultiPageDHtmlDialog](#cmultipagedhtmldialog)|Erstellt ein mehrseitigen (Assistenten-Stil) DHTML-Dialogfeld-Objekt.|  
|[CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog](#cmultipagedhtmldialog__~cmultipagedhtmldialog)|Zerstört ein mehrseitigen DHTML-Dialogfeldobjekt.|  
  
## <a name="remarks"></a>Hinweise  
 Der Mechanismus für diese Vorgehensweise ist ein [DHTML- und URL-ereigniszuordnung](dhtml-event-maps.md), enthält die ereigniszuordnungen für jede Seite eingebettet.  
  
## <a name="example"></a>Beispiel  
 Diese mehrseitige Dialogfeld geht davon aus drei HTML-Ressourcen, die von einfachen Assistenten-ähnliche Funktionalität zu definieren. Die erste Seite verfügt über eine `Next` Schaltfläche, die zweite eine **Prev** und `Next` Schaltfläche und das dritte einen **Prev** Schaltfläche. Wenn eine der Schaltflächen geklickt wird, eine Ereignishandlerfunktion aufruft [CDHtmlDialog::LoadFromResource](../../mfc/reference/cdhtmldialog-class.md#loadfromresource) die entsprechende Seite neue zu laden.  
  
 Die wichtigen Teile der Klassendeklaration (in CMyMultiPageDlg.h):  
  
 [!code-cpp[NVC_MFCDocView#181](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_1.h)]  
  
 Die wichtigen Teile der Implementierung der Klasse (in CMyMultipageDlg.cpp):  
  
 [!code-cpp[NVC_MFCDocView#182](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDHtmlSinkHandlerBase2`  
  
 `CDHtmlSinkHandlerBase1`  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDHtmlSinkHandler`  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDHtmlEventSink`  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)  
  
 `CMultiPageDHtmlDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdhtml.h  
  
##  <a name="cmultipagedhtmldialog"></a>  CMultiPageDHtmlDialog::CMultiPageDHtmlDialog  
 Erstellt ein mehrseitigen (Assistenten-Stil) DHTML-Dialogfeld-Objekt.  
  
```  
CMultiPageDHtmlDialog(
    LPCTSTR lpszTemplateName,  
    LPCTSTR szHtmlResID = NULL,  
    CWnd* pParentWnd = NULL);

 
CMultiPageDHtmlDialog(
    UINT nIDTemplate,  
    UINT nHtmlResID = 0,  
    CWnd* pParentWnd = NULL);  
  
CMultiPageDHtmlDialog();
```  
  
### <a name="parameters"></a>Parameter  
 `lpszTemplateName`  
 Die Null-terminierte Zeichenfolge, die eine Dialogfeldvorlagen-Ressource im Dialogfeld heißt.  
  
 `szHtmlResID`  
 Die Null-terminierte Zeichenfolge, die den Namen des HTML-Ressource ist.  
  
 `pParentWnd`  
 Ein Zeiger auf den übergeordneten oder Besitzer-Fensterobjekt (des Typs [CWnd](../../mfc/reference/cwnd-class.md)), der das Dialogfeldobjekt angehört. Ist er **NULL**, dem Dialogfeldobjekt übergeordnete Fenster auf das Hauptanwendungsfenster festgelegt ist.  
  
 `nIDTemplate`  
 Enthält die ID einer Dialogfeldvorlagen-Ressource im Dialogfeld an.  
  
 `nHtmlResID`  
 Enthält die ID-Nummer, der eine HTML-Ressource an.  
  
##  <a name="_dtorcmultipagedhtmldialog"></a>  CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog  
 Zerstört ein mehrseitigen DHTML-Dialogfeldobjekt.  
  
```  
virtual ~CMultiPageDHtmlDialog();
```  
  
## <a name="see-also"></a>Siehe auch  
 [CDHtmlDialog-Klasse](../../mfc/reference/cdhtmldialog-class.md)
