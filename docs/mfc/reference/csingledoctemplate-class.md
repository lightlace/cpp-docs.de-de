---
title: CSingleDocTemplate-Klasse
ms.date: 11/04/2016
f1_keywords:
- CSingleDocTemplate
- AFXWIN/CSingleDocTemplate
- AFXWIN/CSingleDocTemplate::CSingleDocTemplate
helpviewer_keywords:
- CSingleDocTemplate [MFC], CSingleDocTemplate
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
ms.openlocfilehash: fe85119761d2b56ca72c8efff00664c62d4767bb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299529"
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

Eine SDI-Anwendung verwendet das Hauptrahmenfenster, ein Dokument anzuzeigen. zu einem Zeitpunkt kann nur ein Dokument geöffnet sein.

Eine Dokumentvorlage definiert die Beziehung zwischen drei Typen von Klassen:

- Eine Dokumentenklasse, die Sie von abgeleitet werden `CDocument`.

- Eine Ansichtsklasse, die Daten aus der Dokumentenklasse, die oben aufgeführten anzeigt. Sie können diese Klasse von ableiten `CView`, `CScrollView`, `CFormView`, oder `CEditView`. (Sie können auch `CEditView` direkt.)

- Ein Frame Fenster-Klasse, die die Sicht enthält. Für eine SDI-Dokumentvorlage, Sie können diese Klasse von ableiten `CFrameWnd`; Wenn Sie nicht, zum Anpassen des Verhaltens der Haupt-benötigen frame-Fensters, können Sie mit `CFrameWnd` direkt, ohne eine eigene Klasse ableiten.

Eine SDI-Anwendung unterstützt einen Typ des Dokuments, in der Regel, es gelten somit nur eine `CSingleDocTemplate` Objekt. Zu einem Zeitpunkt kann nur ein Dokument geöffnet sein.

Sie müssen keine Member aufzurufen `CSingleDocTemplate` außer den Konstruktor. Die Framework-Handles `CSingleDocTemplate` Objekte intern.

Weitere Informationen zur Verwendung von `CSingleDocTemplate`, finden Sie unter [Dokumentvorlagen und der Erstellungsvorgang für Dokumente und Ansichten](../../mfc/document-templates-and-the-document-view-creation-process.md).

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

*nIDResource*<br/>
Gibt die ID der mit dem Dokument verwendeten Ressourcen. Dies kann im Menü "," Symbol "," Zugriffstastentabelle "und" Zeichenfolgenressourcen enthalten.

Die Zeichenfolgenressource besteht aus bis zu sieben Teilzeichenfolgen, die durch das Zeichen '\n' getrennte (das Zeichen '\n' wird als Platzhalter benötigt, wenn eine untergeordnete Zeichenfolge nicht enthalten ist; nachfolgende '\n'-Zeichen sind jedoch nicht erforderlich); Diese Teilzeichenfolgen beschreiben den Dokumenttyp an. Weitere Informationen zu den Teilzeichenfolgen, finden Sie unter [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Diese Zeichenfolgenressource in die Ressourcendatei der Anwendung gefunden. Zum Beispiel:

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_MAINFRAME "MyCalc Windows Application\nSheet\nWorksheet\n Worksheets (*.myc)\n.myc\nMyCalcSheet\n MyCalc Worksheet"
END
```

Sie können diese Zeichenfolge, die mit den Zeichenfolgen-Editor bearbeiten. die gesamte Zeichenfolge wird als einzelner Eintrag in den Editor für Zeichenfolgen, nicht als sieben separate Einträge angezeigt.

Weitere Informationen zu dieser Ressourcentypen finden Sie unter den [Zeichenfolgen-Editor](../../windows/string-editor.md).

*pDocClass*<br/>
Verweist auf die `CRuntimeClass` Objekt der Document-Klasse. Diese Klasse ist eine `CDocument`-abgeleitete Klasse, die Sie definieren, um die Darstellung von Dokumenten.

*pFrameClass*<br/>
Verweist auf die `CRuntimeClass` Objekt das Rahmenfenster (Klasse). Diese Klasse kann sein, eine `CFrameWnd`-abgeleitete Klasse, oder es kann sein `CFrameWnd` selbst, wenn Sie Standardverhalten für das Hauptrahmenfenster verwenden möchten.

*pViewClass*<br/>
Verweist auf die `CRuntimeClass` Objekt der Klasse anzeigen. Diese Klasse ist eine `CView`-abgeleitete Klasse, die Sie definieren, um die Anzeige von Dokumenten.

### <a name="remarks"></a>Hinweise

Dynamisch Zuordnen einer `CSingleDocTemplate` -Objekt und übergeben es an `CWinApp::AddDocTemplate` aus der `InitInstance` Memberfunktion der Anwendungsklasse.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocViewSDI#13](../../mfc/codesnippet/cpp/csingledoctemplate-class_1.cpp)]

[!code-cpp[NVC_MFCDocViewSDI#14](../../mfc/codesnippet/cpp/csingledoctemplate-class_2.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel DOCKTOOL](../../visual-cpp-samples.md)<br/>
[CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)<br/>
[CDocument-Klasse](../../mfc/reference/cdocument-class.md)<br/>
[CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)<br/>
[CMultiDocTemplate-Klasse](../../mfc/reference/cmultidoctemplate-class.md)<br/>
[CView-Klasse](../../mfc/reference/cview-class.md)<br/>
[CWinApp-Klasse](../../mfc/reference/cwinapp-class.md)
