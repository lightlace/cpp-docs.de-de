---
title: CMultiDocTemplate Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMultiDocTemplate
- AFXWIN/CMultiDocTemplate
- AFXWIN/CMultiDocTemplate::CMultiDocTemplate
dev_langs:
- C++
helpviewer_keywords:
- MDI, template
- CMultiDocTemplate class
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
caps.latest.revision: 21
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
ms.openlocfilehash: 6e58325cd4dcaec01bf8a76006bb397fccd9a171
ms.lasthandoff: 02/24/2017

---
# <a name="cmultidoctemplate-class"></a>CMultiDocTemplate-Klasse
Definiert eine Dokumentvorlage, welche die Multiple Document Interface (MDI) implementiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMultiDocTemplate : public CDocTemplate  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMultiDocTemplate::CMultiDocTemplate](#cmultidoctemplate)|Erstellt ein `CMultiDocTemplate`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 MDI-Anwendung verwendet das Hauptrahmenfenster als einen Arbeitsbereich, in dem der Benutzer mindestens NULL Dokumentrahmenfenster öffnen kann,, der jeweils ein Dokument anzeigt. Eine ausführlichere Beschreibung des MDI, finden Sie unter *Richtlinien der Windows-Benutzeroberfläche für den Softwareentwurf*.  
  
 Eine Dokumentvorlage definiert die Beziehungen zwischen drei Typen von Klassen:  
  
-   Eine Dokumentenklasse, die Ableitung von [CDocument](../../mfc/reference/cdocument-class.md).  
  
-   Eine View-Klasse, die Daten aus der oben aufgeführten Dokumentklasse anzeigt. Sie können diese Klasse von ableiten [CView](../../mfc/reference/cview-class.md), `CScrollView`, `CFormView`, oder `CEditView`. (Sie können auch `CEditView` direkt.)  
  
-   Ein Frame Fenster-Klasse, die die Sicht enthält. Für eine MDI-Dokumentvorlage, leiten Sie diese Klasse von `CMDIChildWnd`, oder wenn Sie nicht das Verhalten der Dokumentrahmenfenster anpassen müssen, können Sie [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) direkt, ohne eine eigene Klasse ableiten.  
  
 MDI-Anwendung kann mehr als einen Typ des Dokuments unterstützen und Dokumente verschiedener Typen können gleichzeitig geöffnet sein. Ihre Anwendung hat eine Dokumentvorlage für jeden Dokumenttyp, die es unterstützt. Z. B. wenn die MDI-Anwendung Kalkulationstabellen und Dokumente unterstützt, die Anwendung verfügt über zwei `CMultiDocTemplate` Objekte.  
  
 Die Anwendung verwendet die Dokument-Vorlagen aus, wenn der Benutzer ein neues Dokument erstellt. Wenn die Anwendung mehr als einen Typ des Dokuments unterstützt, kann das Framework Ruft die Namen der unterstützten Dokumenttypen die Dokumentvorlagen ab und zeigt sie in einer Liste im Dialogfeld neue Datei. Nachdem der Benutzer ein Dokument ausgewählt, wird die Anwendung erstellt ein Dokument Class-Objekt, ein Frame Window-Objekt und ein Objekt und fügt sie miteinander.  
  
 Sie müssen keine Memberfunktionen Aufrufen von `CMultiDocTemplate` außer den Konstruktor. Die Framework-Handles `CMultiDocTemplate` Objekte intern.  
  
 Weitere Informationen zu `CMultiDocTemplate`, finden Sie unter [Dokumentvorlagen und der Erstellungsvorgang für Dokument und Ansicht](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CMultiDocTemplate`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cmultidoctemplate"></a>CMultiDocTemplate::CMultiDocTemplate  
 Erstellt ein `CMultiDocTemplate`-Objekt.  
  
```  
CMultiDocTemplate(
    UINT nIDResource,  
    CRuntimeClass* pDocClass,  
    CRuntimeClass* pFrameClass,  
    CRuntimeClass* pViewClass);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDResource`  
 Gibt die ID der mit dem Dokumenttyp verwendeten Ressourcen. Dies kann im Menü, Symbol, Zugriffstastentabelle und Zeichenfolgenressourcen enthalten.  
  
 Die Zeichenfolgenressource besteht aus bis zu sieben Teilzeichenfolgen, die durch das Zeichen '\n' getrennte (das Zeichen '\n' wird als Platzhalter benötigt, wenn eine Teilzeichenfolge nicht enthalten ist; nachfolgende '\n'-Zeichen sind jedoch nicht erforderlich) Diese Teilzeichenfolgen beschreiben den Dokumenttyp. Informationen zu den Teilzeichenfolgen, finden Sie unter [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Diese Zeichenfolgenressource befindet sich in der Ressourcendatei der Anwendung. Zum Beispiel:  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"`  
  
 `END`  
  
 Beachten Sie, dass die Zeichenfolge mit dem Zeichen '\n' beginnt. Dies ist die erste Teilzeichenfolge wird nicht für MDI-Anwendung verwendet und ist daher nicht enthalten. Sie können diese Zeichenfolge im Zeichenfolgen-Editor bearbeiten. die gesamte Zeichenfolge wird als einzelner Eintrag in der Zeichenfolgen-Editor nicht als sieben separate Einträge angezeigt.  
  
 Weitere Informationen zu diesen Ressourcen finden Sie unter [-Ressourcen-Editoren](../../windows/resource-editors.md).  
  
 `pDocClass`  
 Verweist auf die `CRuntimeClass` Objekt der Document-Klasse. Diese Klasse ist eine **CDocument**-abgeleitete Klasse, die Sie zur Darstellung von Dokumenten definieren.  
  
 `pFrameClass`  
 Verweist auf die `CRuntimeClass` Objekt der Klasse Rahmenfenster. Diese Klasse kann eine `CMDIChildWnd`-abgeleitete Klasse, oder es kann `CMDIChildWnd` selbst, wenn Sie für Ihre Dokumentrahmenfenster Standardverhalten verwenden möchten.  
  
 `pViewClass`  
 Verweist auf die `CRuntimeClass` Objekt der Klasse anzeigen. Diese Klasse ist eine `CView`-abgeleitete Klasse, die Sie zur Anzeige von Dokumenten definieren.  
  
### <a name="remarks"></a>Hinweise  
 Eine dynamische Zuordnung von `CMultiDocTemplate` -Objekt für jeden Dokumenttyp, die Ihre Anwendung unterstützt, und übergeben jeweils `CWinApp::AddDocTemplate` aus der `InitInstance` -Memberfunktion der Anwendungsklasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#92;](../../mfc/codesnippet/cpp/cmultidoctemplate-class_1.cpp)]  
  
 Hier ist ein zweites Beispiel.  
  
 [!code-cpp[NVC_MFCDocView&#93;](../../mfc/codesnippet/cpp/cmultidoctemplate-class_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)   
 [CSingleDocTemplate-Klasse](../../mfc/reference/csingledoctemplate-class.md)   
 [CWinApp-Klasse](../../mfc/reference/cwinapp-class.md)

