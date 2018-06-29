---
title: CSingleDocTemplate Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSingleDocTemplate
- AFXWIN/CSingleDocTemplate
- AFXWIN/CSingleDocTemplate::CSingleDocTemplate
dev_langs:
- C++
helpviewer_keywords:
- CSingleDocTemplate [MFC], CSingleDocTemplate
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
author: mikeblome
ms.author: mblome
ms.openlocfilehash: efdd8f5b806b7e5745aed0091a2638c8592a6ecc
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079064"
---
# <a name="csingledoctemplate-class"></a>CSingleDocTemplate-Klasse
Definiert eine Dokumentvorlage, welche die Single Document Interface (SDI) implementiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSingleDocTemplate : public CDocTemplate  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSingleDocTemplate::CSingleDocTemplate](#csingledoctemplate)|Erstellt ein `CSingleDocTemplate`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 SDI-Anwendung verwendet das Hauptrahmenfenster, ein Dokument anzuzeigen. jeweils kann nur ein Dokument geöffnet sein.  
  
 Eine Dokumentvorlage definiert die Beziehung zwischen drei Typen von Klassen:  
  
-   Eine Dokumentenklasse, die Ableitung von `CDocument`.  
  
-   Eine View-Klasse, die Daten aus den oben aufgeführten Dokumentklasse anzeigt. Sie können diese Klasse von ableiten `CView`, `CScrollView`, `CFormView`, oder `CEditView`. (Sie können auch `CEditView` direkt.)  
  
-   Ein Frame Fenster-Klasse, die die Sicht enthält. Für eine SDI-Dokumentvorlage, leiten Sie diese Klasse von `CFrameWnd`; Wenn Sie nicht, zum Anpassen des Verhaltens der Hauptelemente benötigen frame-Fensters, können Sie `CFrameWnd` direkt, ohne eine eigene Klasse ableiten.  
  
 SDI-Anwendung in der Regel einen Typ von Dokument, unterstützt, deshalb nur eine `CSingleDocTemplate` Objekt. Jeweils kann nur ein Dokument geöffnet sein.  
  
 Sie müssen keine Memberfunktionen Aufrufen von `CSingleDocTemplate` mit Ausnahme den Konstruktor. Die Framework-Handles `CSingleDocTemplate` intern Objekte.  
  
 Weitere Informationen zur Verwendung von `CSingleDocTemplate`, finden Sie unter [Dokumentvorlagen und der Erstellungsvorgang für die Dokument-/Ansichtarchitektur](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CSingleDocTemplate`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="csingledoctemplate"></a>  CSingleDocTemplate::CSingleDocTemplate  
 Erstellt ein `CSingleDocTemplate`-Objekt.  
  
```  
CSingleDocTemplate(
    UINT nIDResource,  
    CRuntimeClass* pDocClass,  
    CRuntimeClass* pFrameClass,  
    CRuntimeClass* pViewClass);
```  
  
### <a name="parameters"></a>Parameter  
 *nIDResource*  
 Gibt die ID der Ressourcen, mit dem Dokument verwendet. Dies kann im Menü, Symbol Zugriffstastentabelle und Zeichenfolgenressourcen umfassen.  
  
 Eine Zeichenfolgenressource besteht aus bis zu sieben Teilzeichenfolgen, getrennt durch das Zeichen "\n" (das Zeichen "\n" ist als Platzhalter erforderlich, wenn eine Teilzeichenfolge nicht angegeben wird; nachfolgende "\n"-Zeichen sind jedoch nicht erforderlich) Diese Teilzeichenfolgen beschreiben den "Document". Informationen zu den Teilzeichenfolgen finden Sie unter [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Diese Zeichenfolgenressource in der Ressourcendatei für die Anwendung gefunden. Zum Beispiel:  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_MAINFRAME "MyCalc Windows Application\nSheet\nWorksheet\n Worksheets (*.myc)\n.myc\nMyCalcSheet\n MyCalc Worksheet"`  
  
 `END`  
  
 Sie können diese Zeichenfolge mit der Zeichenfolgen-Editor bearbeiten. die gesamte Zeichenfolge wird als einzelner Eintrag in Zeichenfolgen-Editor nicht als sieben trennen Sie die Einträge angezeigt.  
  
 Weitere Informationen zu diesen Ressourcen finden Sie unter der [Zeichenfolgen-Editor](../../windows/string-editor.md).  
  
 *pDocClass*  
 Verweist auf die `CRuntimeClass` Objekt der Dokumentklasse. Diese Klasse ist eine `CDocument`-abgeleitete Klasse, die Sie definieren, um Ihre Dokumente darzustellen.  
  
 *pFrameClass*  
 Verweist auf die `CRuntimeClass` Objekt von der Rahmenfenster (Klasse). Diese Klasse kann eine `CFrameWnd`-abgeleitete Klasse, oder es kann `CFrameWnd` selbst, wenn Sie Standardverhalten für das Hauptrahmenfenster verwenden möchten.  
  
 *pViewClass*  
 Verweist auf die `CRuntimeClass` Objekt der Ansichtsklasse. Diese Klasse ist eine `CView`-abgeleitete Klasse, die Sie definieren, um Ihre Dokumente anzuzeigen.  
  
### <a name="remarks"></a>Hinweise  
 Dynamisch Zuordnen einer `CSingleDocTemplate` Objekt, und übergeben Sie sie an `CWinApp::AddDocTemplate` aus der `InitInstance` Memberfunktion Ihrer Anwendung-Klasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocViewSDI#13](../../mfc/codesnippet/cpp/csingledoctemplate-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocViewSDI#14](../../mfc/codesnippet/cpp/csingledoctemplate-class_2.cpp)]  
  
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
