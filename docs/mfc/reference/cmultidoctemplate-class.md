---
title: CMultiDocTemplate Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMultiDocTemplate
- AFXWIN/CMultiDocTemplate
- AFXWIN/CMultiDocTemplate::CMultiDocTemplate
dev_langs:
- C++
helpviewer_keywords:
- CMultiDocTemplate [MFC], CMultiDocTemplate
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b53228b6983c0293eb288cd0f38669d1b5db928
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371581"
---
# <a name="cmultidoctemplate-class"></a>CMultiDocTemplate-Klasse
Definiert eine Dokumentvorlage, welche die Multiple Document Interface (MDI) implementiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMultiDocTemplate : public CDocTemplate  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMultiDocTemplate::CMultiDocTemplate](#cmultidoctemplate)|Erstellt ein `CMultiDocTemplate`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Eine MDI-Anwendung verwendet das Hauptrahmenfenster als einen Arbeitsbereich in dem der Benutzer mindestens NULL Dokumentrahmenfenster öffnen kann, von der jeder ein Dokument zeigt. Eine ausführlichere Beschreibung des MDI, finden Sie unter *Richtlinien zur Windows-Benutzeroberfläche für den Softwareentwurf*.  
  
 Eine Dokumentvorlage definiert die Beziehungen zwischen drei Typen von Klassen:  
  
-   Eine Dokumentenklasse, die Ableitung von [CDocument](../../mfc/reference/cdocument-class.md).  
  
-   Eine View-Klasse, die Daten aus den oben aufgeführten Dokumentklasse anzeigt. Sie können diese Klasse von ableiten [CView](../../mfc/reference/cview-class.md), `CScrollView`, `CFormView`, oder `CEditView`. (Sie können auch `CEditView` direkt.)  
  
-   Ein Frame Fenster-Klasse, die die Sicht enthält. Für eine MDI-Dokumentvorlage, leiten Sie diese Klasse von `CMDIChildWnd`, oder wenn Sie zum Anpassen des Verhaltens von der Dokumentrahmenfenster benötigen, können Sie [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) direkt, ohne eine eigene Klasse ableiten.  
  
 Eine MDI-Anwendung kann mehr als einen Typ von Dokument unterstützen und Dokumente verschiedener Typen können zur gleichen Zeit geöffnet sein. Die Anwendung verfügt eine Dokumentvorlage für jeden Dokumenttyp, die dies unterstützt. Beispielsweise, wenn die MDI-Anwendung Kalkulationstabellen und Textdokumente unterstützt, die Anwendung verfügt über zwei `CMultiDocTemplate` Objekte.  
  
 Die Anwendung verwendet die Vorlage(n) Dokument aus, wenn der Benutzer ein neues Dokument erstellt. Wenn die Anwendung mehr als ein Typ des Dokuments unterstützt, kann das Framework Ruft die Namen der unterstützten Dokumenttypen aus den Dokumentvorlagen ab und zeigt sie in einer Liste im Dialogfeld neue Datei. Sobald der Benutzer ein Dokument ausgewählt hat, wird die Anwendung eines Klassenobjekts Dokument, einem Frame-Fensterobjekt und ein Objekt erstellt und angefügt, das miteinander.  
  
 Sie müssen keine Memberfunktionen Aufrufen von `CMultiDocTemplate` mit Ausnahme den Konstruktor. Die Framework-Handles `CMultiDocTemplate` intern Objekte.  
  
 Weitere Informationen zu `CMultiDocTemplate`, finden Sie unter [Dokumentvorlagen und der Erstellungsvorgang für die Dokument-/Ansichtarchitektur](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CMultiDocTemplate`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cmultidoctemplate"></a>  CMultiDocTemplate::CMultiDocTemplate  
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
 Gibt die ID der Ressourcen, mit dem Dokument verwendet. Dies kann im Menü, Symbol Zugriffstastentabelle und Zeichenfolgenressourcen umfassen.  
  
 Eine Zeichenfolgenressource besteht aus bis zu sieben Teilzeichenfolgen, getrennt durch das Zeichen "\n" (das Zeichen "\n" ist als Platzhalter erforderlich, wenn eine Teilzeichenfolge nicht angegeben wird; nachfolgende "\n"-Zeichen sind jedoch nicht erforderlich) Diese Teilzeichenfolgen beschreiben den "Document". Informationen zu den Teilzeichenfolgen, finden Sie unter [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Diese Zeichenfolgenressource in der Ressourcendatei für die Anwendung gefunden. Zum Beispiel:  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"`  
  
 `END`  
  
 Beachten Sie, dass die Zeichenfolge mit einem "\n"-Zeichen beginnt. Dies ist, da die erste Teilzeichenfolge für MDI-Anwendungen nicht verwendet wird und daher nicht enthalten ist. Sie können diese Zeichenfolge mit der Zeichenfolgen-Editor bearbeiten. die gesamte Zeichenfolge wird als einzelner Eintrag in Zeichenfolgen-Editor nicht als sieben trennen Sie die Einträge angezeigt.  
  
 Weitere Informationen zu diesen Ressourcen finden Sie unter [Ressourcen-Editoren](../../windows/resource-editors.md).  
  
 `pDocClass`  
 Verweist auf die `CRuntimeClass` Objekt der Dokumentklasse. Diese Klasse ist eine **CDocument**-abgeleitete Klasse, die Sie definieren, um Ihre Dokumente darzustellen.  
  
 `pFrameClass`  
 Verweist auf die `CRuntimeClass` Objekt der Klasse Rahmenfenster. Diese Klasse kann eine `CMDIChildWnd`-abgeleitete Klasse, oder es kann `CMDIChildWnd` selbst, wenn Sie für Ihre Dokumentrahmenfenster Standardverhalten verwenden möchten.  
  
 `pViewClass`  
 Verweist auf die `CRuntimeClass` Objekt der Ansichtsklasse. Diese Klasse ist eine `CView`-abgeleitete Klasse, die Sie definieren, um Ihre Dokumente anzuzeigen.  
  
### <a name="remarks"></a>Hinweise  
 Eine dynamische Speicherzuordnung `CMultiDocTemplate` Objekt für jeden Dokumenttyp, die Ihre Anwendung unterstützt, und übergeben jeder einzelnen `CWinApp::AddDocTemplate` aus der `InitInstance` Memberfunktion der Anwendungsklasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#92](../../mfc/codesnippet/cpp/cmultidoctemplate-class_1.cpp)]  
  
 So sieht ein zweites Beispiel aus.  
  
 [!code-cpp[NVC_MFCDocView#93](../../mfc/codesnippet/cpp/cmultidoctemplate-class_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)   
 [CSingleDocTemplate-Klasse](../../mfc/reference/csingledoctemplate-class.md)   
 [CWinApp-Klasse](../../mfc/reference/cwinapp-class.md)
