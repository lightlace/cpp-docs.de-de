---
title: CSingleDocTemplate Class | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSingleDocTemplate
- AFXWIN/CSingleDocTemplate
- AFXWIN/CSingleDocTemplate::CSingleDocTemplate
dev_langs:
- C++
helpviewer_keywords:
- templates, SDI
- document templates, single
- single document interface (SDI), applications
- CSingleDocTemplate class
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
caps.latest.revision: 23
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
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 78e288dd958e73495a8d513d7fe3427ccc956a61
ms.lasthandoff: 02/24/2017

---
# <a name="csingledoctemplate-class"></a>CSingleDocTemplate-Klasse
Definiert eine Dokumentvorlage, welche die Single Document Interface (SDI) implementiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSingleDocTemplate : public CDocTemplate  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSingleDocTemplate::CSingleDocTemplate](#csingledoctemplate)|Erstellt ein `CSingleDocTemplate`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Eine SDI-Anwendung verwendet das Hauptrahmenfenster, ein Dokument anzuzeigen. jeweils kann nur ein Dokument geöffnet sein.  
  
 Eine Dokumentvorlage definiert die Beziehung zwischen drei Klassen:  
  
-   Eine Dokumentenklasse, die Ableitung von **CDocument**.  
  
-   Eine View-Klasse, die Daten aus der oben aufgeführten Dokumentklasse anzeigt. Sie können diese Klasse von ableiten `CView`, `CScrollView`, `CFormView`, oder `CEditView`. (Sie können auch `CEditView` direkt.)  
  
-   Ein Frame Fenster-Klasse, die die Sicht enthält. Für eine SDI-Dokumentvorlage, leiten Sie diese Klasse von `CFrameWnd`; Wenn Sie nicht, zum Anpassen des Verhaltens des Hauptfensters benötigen frame-Fensters, können Sie `CFrameWnd` direkt, ohne eine eigene Klasse ableiten.  
  
 Eine SDI-Anwendung in der Regel unterstützt einen Dokument, so dass nur ein `CSingleDocTemplate` Objekt. Jeweils kann nur ein Dokument geöffnet sein.  
  
 Sie müssen keine Memberfunktionen Aufrufen von `CSingleDocTemplate` außer den Konstruktor. Die Framework-Handles `CSingleDocTemplate` Objekte intern.  
  
 Weitere Informationen zur Verwendung von `CSingleDocTemplate`, finden Sie unter [Dokumentvorlagen und der Erstellungsvorgang für Dokument und Ansicht](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CSingleDocTemplate`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="csingledoctemplate"></a>CSingleDocTemplate::CSingleDocTemplate  
 Erstellt ein `CSingleDocTemplate`-Objekt.  
  
```  
CSingleDocTemplate(
    UINT nIDResource,  
    CRuntimeClass* pDocClass,  
    CRuntimeClass* pFrameClass,  
    CRuntimeClass* pViewClass);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDResource`  
 Gibt die ID der mit dem Dokumenttyp verwendeten Ressourcen. Dies kann im Menü, Symbol, Zugriffstastentabelle und Zeichenfolgenressourcen enthalten.  
  
 Die Zeichenfolgenressource besteht aus bis zu sieben Teilzeichenfolgen, die durch das Zeichen '\n' getrennte (das Zeichen '\n' wird als Platzhalter benötigt, wenn eine Teilzeichenfolge nicht enthalten ist; nachfolgende '\n'-Zeichen sind jedoch nicht erforderlich) Diese Teilzeichenfolgen beschreiben den Dokumenttyp. Weitere Informationen zu den Teilzeichenfolgen, finden Sie unter [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Diese Zeichenfolgenressource befindet sich in der Ressourcendatei der Anwendung. Zum Beispiel:  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_MAINFRAME "MyCalc Windows Application\nSheet\nWorksheet\n Worksheets (*.myc)\n.myc\nMyCalcSheet\n MyCalc Worksheet"`  
  
 `END`  
  
 Sie können diese Zeichenfolge im Zeichenfolgen-Editor bearbeiten. die gesamte Zeichenfolge wird als einzelner Eintrag in der Zeichenfolgen-Editor nicht als sieben separate Einträge angezeigt.  
  
 Weitere Informationen zu diesen Ressourcen finden Sie unter der [Zeichenfolgen-Editor](../../windows/string-editor.md).  
  
 `pDocClass`  
 Verweist auf die `CRuntimeClass` Objekt der Document-Klasse. Diese Klasse ist eine **CDocument**-abgeleitete Klasse, die Sie zur Darstellung von Dokumenten definieren.  
  
 `pFrameClass`  
 Verweist auf die `CRuntimeClass` Objekt das Rahmenfenster (Klasse). Diese Klasse kann eine `CFrameWnd`-abgeleitete Klasse, oder es kann `CFrameWnd` selbst, wenn Sie Standardverhalten für das Hauptrahmenfenster verwenden möchten.  
  
 `pViewClass`  
 Verweist auf die `CRuntimeClass` Objekt der Klasse anzeigen. Diese Klasse ist eine `CView`-abgeleitete Klasse, die Sie zur Anzeige von Dokumenten definieren.  
  
### <a name="remarks"></a>Hinweise  
 Dynamisch eine `CSingleDocTemplate` Objekt und übergeben es an `CWinApp::AddDocTemplate` aus der `InitInstance` -Memberfunktion der Anwendungsklasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocViewSDI&#13;](../../mfc/codesnippet/cpp/csingledoctemplate-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocViewSDI&14;](../../mfc/codesnippet/cpp/csingledoctemplate-class_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel DOCKTOOL](../../visual-cpp-samples.md)   
 [CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)   
 [CDocument-Klasse](../../mfc/reference/cdocument-class.md)   
 [CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)   
 [CMultiDocTemplate-Klasse](../../mfc/reference/cmultidoctemplate-class.md)   
 [CView-Klasse](../../mfc/reference/cview-class.md)   
 [CWinApp-Klasse](../../mfc/reference/cwinapp-class.md)

