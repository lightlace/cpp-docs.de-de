---
title: Klasse CMultiPageDHtmlDialog | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog
dev_langs:
- C++
helpviewer_keywords:
- CMultiPageDHtmlDialog class
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
caps.latest.revision: 22
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c00af20731b2c47a0074366722da3f4a0711ef85
ms.lasthandoff: 02/24/2017

---
# <a name="cmultipagedhtmldialog-class"></a>CMultiPageDHtmlDialog-Klasse
Ein mehrseitiges Dialogfeld zeigt mehrere HTML-Seiten sequenziell an und behandelt die Ereignisse jeder Seite.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMultiPageDHtmlDialog : public CDHtmlDialog  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMultiPageDHtmlDialog::CMultiPageDHtmlDialog](#cmultipagedhtmldialog)|Erstellt ein mehrseitiges (assistentenartige) DHTML-Dialogfeld-Objekt.|  
|[CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog](#cmultipagedhtmldialog__~cmultipagedhtmldialog)|Zerstört ein mehrseitiges DHTML Dialog-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Der Mechanismus hierfür ist ein [DHTML und URL-ereigniszuordnung](http://msdn.microsoft.com/en-us/2a7332f0-79d7-46e4-b816-0a618c46777a), enthält die [ereigniszuordnungen eingebettet](http://msdn.microsoft.com/library/5346210f-f8b7-4e28-9d2c-d9d7fd42421d) für jede Seite.  
  
## <a name="example"></a>Beispiel  
 Diese mehrseitige Dialogfeld geht davon aus drei HTML-Ressourcen, die einfachen Assistenten-ähnliche Funktionen definieren. Ist die erste Seite einer `Next` Schaltfläche, die zweite eine **Prev** und `Next` Schaltfläche, und die dritte ein **Prev** Schaltfläche. Wenn eine der Schaltflächen geklickt wird, wird eine Handlerfunktion aufgerufen [CDHtmlDialog::LoadFromResource](../../mfc/reference/cdhtmldialog-class.md#loadfromresource) zum Laden der entsprechenden neuen Seite.  
  
 Die wichtigen Teile der Klassendeklaration (in CMyMultiPageDlg.h):  
  
 [!code-cpp[NVC_MFCDocView&#181;](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_1.h)]  
  
 Die wichtigen Teile der Implementierung der Klasse (in CMyMultipageDlg.cpp):  
  
 [!code-cpp[NVC_MFCDocView&#182;](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
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
  
##  <a name="cmultipagedhtmldialog"></a>CMultiPageDHtmlDialog::CMultiPageDHtmlDialog  
 Erstellt ein mehrseitiges (assistentenartige) DHTML-Dialogfeld-Objekt.  
  
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
 Die auf Null endende Zeichenfolge, die den Namen des eine Dialogfeldvorlagen-Ressource im Dialogfeld.  
  
 `szHtmlResID`  
 Die auf Null endende Zeichenfolge, die den Namen der HTML-Ressource ist.  
  
 `pParentWnd`  
 Ein Zeiger auf das übergeordnete Element oder Besitzer (des Typs [CWnd](../../mfc/reference/cwnd-class.md)), der das Dialogfeldobjekt angehört. Ist dies **NULL**, wird das Dialogfeldobjekt übergeordnete Fenster zum Hauptfenster der Anwendung festgelegt.  
  
 `nIDTemplate`  
 Enthält die ID-Nummer einer Dialogfeldvorlagen-Ressource im Dialogfeld.  
  
 `nHtmlResID`  
 Enthält die ID-Nummer, der eine HTML-Ressource.  
  
##  <a name="_dtorcmultipagedhtmldialog"></a>CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog  
 Zerstört ein mehrseitiges DHTML Dialog-Objekt.  
  
```  
virtual ~CMultiPageDHtmlDialog();
```  
  
## <a name="see-also"></a>Siehe auch  
 [CDHtmlDialog-Klasse](../../mfc/reference/cdhtmldialog-class.md)

