---
title: CMultiDocTemplate-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMultiDocTemplate
- AFXWIN/CMultiDocTemplate
- AFXWIN/CMultiDocTemplate::CMultiDocTemplate
helpviewer_keywords:
- CMultiDocTemplate [MFC], CMultiDocTemplate
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
ms.openlocfilehash: 9a1b303924458ab03bc2ec42be1fbc3b2afa64ed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566493"
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

MDI-Anwendung verwendet das Hauptrahmenfenster als einen Arbeitsbereich in dem der Benutzer auf NULL oder mehr Dokumentrahmenfenstern öffnen kann, von der jeder ein Dokument zeigt. Eine ausführlichere Beschreibung der MDI, finden Sie unter *Richtlinien der Windows-Benutzeroberfläche für den Softwareentwurf*.

Eine Dokumentvorlage definiert die Beziehungen zwischen den drei Arten von Klassen:

- Eine Dokumentenklasse, die Sie von abgeleitet werden [CDocument](../../mfc/reference/cdocument-class.md).

- Eine Ansichtsklasse, die Daten aus der Dokumentenklasse, die oben aufgeführten anzeigt. Sie können diese Klasse von ableiten [CView](../../mfc/reference/cview-class.md), `CScrollView`, `CFormView`, oder `CEditView`. (Sie können auch `CEditView` direkt.)

- Ein Frame Fenster-Klasse, die die Sicht enthält. Für eine MDI-Dokumentvorlage, Sie können diese Klasse von ableiten `CMDIChildWnd`, oder, wenn Sie nicht das Verhalten der Dokumentrahmenfenstern anpassen müssen, können Sie [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) direkt, ohne eine eigene Klasse ableiten.

MDI-Anwendung kann mehr als einen Typ des Dokuments unterstützen und Dokumente verschiedener Typen können gleichzeitig geöffnet sein. Ihre Anwendung verfügt über eine Vorlage für Dokumente für jeden Dokumenttyp, die es unterstützt. Z. B. wenn die MDI-Anwendung sowohl Tabellen als auch Text unterstützt, die Anwendung verfügt über zwei `CMultiDocTemplate` Objekte.

Die Anwendung verwendet die Vorlage(n) Dokument aus, wenn der Benutzer ein neues Dokument erstellt. Wenn die Anwendung mehr als einen Typ des Dokuments unterstützt, kann das Framework Ruft die Namen der unterstützten Dokumenttypen die Dokumentvorlagen ab und zeigt sie in einer Liste im Dialogfeld "neue Datei". Nachdem der Benutzer ein Dokument ausgewählt, wird die Anwendung ein Dokumentobjekt-Klasse, ein Frame Window-Objekt und ein Objekt erstellt und angefügt, das miteinander.

Sie müssen keine Member aufzurufen `CMultiDocTemplate` außer den Konstruktor. Die Framework-Handles `CMultiDocTemplate` Objekte intern.

Weitere Informationen zu `CMultiDocTemplate`, finden Sie unter [Dokumentvorlagen und der Erstellungsvorgang für Dokumente und Ansichten](../../mfc/document-templates-and-the-document-view-creation-process.md).

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

*nIDResource*<br/>
Gibt die ID der mit dem Dokument verwendeten Ressourcen. Dies kann im Menü "," Symbol "," Zugriffstastentabelle "und" Zeichenfolgenressourcen enthalten.

Die Zeichenfolgenressource besteht aus bis zu sieben Teilzeichenfolgen, die durch das Zeichen '\n' getrennte (das Zeichen '\n' wird als Platzhalter benötigt, wenn eine untergeordnete Zeichenfolge nicht enthalten ist; nachfolgende '\n'-Zeichen sind jedoch nicht erforderlich); Diese Teilzeichenfolgen beschreiben den Dokumenttyp an. Weitere Informationen dazu, das die Teilzeichenfolgen, finden Sie unter [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Diese Zeichenfolgenressource in die Ressourcendatei der Anwendung gefunden. Zum Beispiel:

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"
END
```

Beachten Sie, dass die Zeichenfolge mit einem '\n'-Zeichen beginnt. Dies ist, da die erste Teilzeichenfolge nicht für MDI-Anwendungen verwendet wird und daher nicht enthalten ist. Sie können diese Zeichenfolge, die mit den Zeichenfolgen-Editor bearbeiten. die gesamte Zeichenfolge wird als einzelner Eintrag in den Editor für Zeichenfolgen, nicht als sieben separate Einträge angezeigt.

Weitere Informationen zu dieser Ressourcentypen finden Sie unter [Ressourcen-Editoren](../../windows/resource-editors.md).

*pDocClass*<br/>
Verweist auf die `CRuntimeClass` Objekt der Document-Klasse. Diese Klasse ist eine `CDocument`-abgeleitete Klasse, die Sie definieren, um die Darstellung von Dokumenten.

*pFrameClass*<br/>
Verweist auf die `CRuntimeClass` Objekt der Klasse Rahmenfenster. Diese Klasse kann sein, eine `CMDIChildWnd`-abgeleitete Klasse, oder es kann sein `CMDIChildWnd` selbst, wenn Sie für Ihre Dokumentrahmenfenstern Standardverhalten verwenden möchten.

*pViewClass*<br/>
Verweist auf die `CRuntimeClass` Objekt der Klasse anzeigen. Diese Klasse ist eine `CView`-abgeleitete Klasse, die Sie definieren, um die Anzeige von Dokumenten.

### <a name="remarks"></a>Hinweise

Dynamisch Zuordnen einer `CMultiDocTemplate` Objekt für jeden Dokumenttyp, der Ihre Anwendung unterstützt, und übergeben für jeden Listener `CWinApp::AddDocTemplate` aus der `InitInstance` Memberfunktion der Anwendungsklasse.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#92](../../mfc/codesnippet/cpp/cmultidoctemplate-class_1.cpp)]

Hier ist ein zweites Beispiel.

[!code-cpp[NVC_MFCDocView#93](../../mfc/codesnippet/cpp/cmultidoctemplate-class_2.cpp)]

## <a name="see-also"></a>Siehe auch

[CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)<br/>
[CSingleDocTemplate-Klasse](../../mfc/reference/csingledoctemplate-class.md)<br/>
[CWinApp-Klasse](../../mfc/reference/cwinapp-class.md)
