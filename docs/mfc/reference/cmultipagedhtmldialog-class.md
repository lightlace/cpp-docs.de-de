---
title: CMultiPageDHtmlDialog-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 51e9b34252b2a3fa7d097914360b9ee24baa8301
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850864"
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
|[CMultiPageDHtmlDialog::CMultiPageDHtmlDialog](#cmultipagedhtmldialog)|Erstellt ein mehrseitigen (Assistenten-ähnlichen) DHTML-Dialogfeld-Objekt.|  
|[CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog](#cmultipagedhtmldialog__~cmultipagedhtmldialog)|Zerstört ein mehrseitigen DHTML-Dialogfeld-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Der Mechanismus hierfür ist eine [DHTML und URL-ereigniszuordnung](dhtml-event-maps.md), enthält die ereigniszuordnungen für jede Seite eingebettet.  
  
## <a name="example"></a>Beispiel  
 Dieses mehrseitige Dialogfeld wird davon ausgegangen, drei HTML-Ressourcen, die einfachen Assistenten-ähnlichen Funktionen zu definieren. Die erste Seite enthält eine **Weiter** Schaltfläche, die zweite eine **Prev** und **Weiter** Schaltfläche, und der dritte einer **Prev** Schaltfläche. Wenn eine der Schaltflächen geklickt wird, wird eine Handlerfunktion aufgerufen [CDHtmlDialog::LoadFromResource](../../mfc/reference/cdhtmldialog-class.md#loadfromresource) zum Laden der entsprechenden neuen Seite.  
  
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
 Erstellt ein mehrseitigen (Assistenten-ähnlichen) DHTML-Dialogfeld-Objekt.  
  
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
 *lpszTemplateName*  
 Die Null-terminierte Zeichenfolge mit dem Namen von einer Ressource im Dialogfeld.  
  
 *szHtmlResID*  
 Die Null-terminierte Zeichenfolge, die den Namen der eine HTML-Ressource ist.  
  
 *pParentWnd*  
 Ein Zeiger auf das übergeordnete Element oder Besitzer Window-Objekt (des Typs [CWnd](../../mfc/reference/cwnd-class.md)) zu dem das Dialogfeldobjekt gehört. Wenn es NULL ist, wird das Dialogfeldobjekt übergeordnete Fenster auf das Hauptanwendungsfenster festgelegt.  
  
 *nIDTemplate*  
 Enthält die ID einer Ressource im Dialogfeld an.  
  
 *nHtmlResID*  
 Enthält die ID-Nummer, der eine HTML-Ressource.  
  
##  <a name="_dtorcmultipagedhtmldialog"></a>  CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog  
 Zerstört ein mehrseitigen DHTML-Dialogfeld-Objekt.  
  
```  
virtual ~CMultiPageDHtmlDialog();
```  
  
## <a name="see-also"></a>Siehe auch  
 [CDHtmlDialog-Klasse](../../mfc/reference/cdhtmldialog-class.md)
