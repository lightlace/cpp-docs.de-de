---
title: COleLinkingDoc-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleLinkingDoc
- AFXOLE/COleLinkingDoc
- AFXOLE/COleLinkingDoc::COleLinkingDoc
- AFXOLE/COleLinkingDoc::Register
- AFXOLE/COleLinkingDoc::Revoke
- AFXOLE/COleLinkingDoc::OnFindEmbeddedItem
- AFXOLE/COleLinkingDoc::OnGetLinkedItem
helpviewer_keywords:
- COleLinkingDoc [MFC], COleLinkingDoc
- COleLinkingDoc [MFC], Register
- COleLinkingDoc [MFC], Revoke
- COleLinkingDoc [MFC], OnFindEmbeddedItem
- COleLinkingDoc [MFC], OnGetLinkedItem
ms.assetid: 9f547f35-2f95-427f-b9c0-85c31940198b
ms.openlocfilehash: c5076ceef0c6626fac0232fadf6818edd78b4ccf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62224362"
---
# <a name="colelinkingdoc-class"></a>COleLinkingDoc-Klasse

Die Basisklasse für OLE-Containerdokumente, die das Verknüpfen mit den enthaltenen eingebetteten Elementen unterstützt.

## <a name="syntax"></a>Syntax

```
class COleLinkingDoc : public COleDocument
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleLinkingDoc::COleLinkingDoc](#colelinkingdoc)|Erstellt ein `COleLinkingDoc`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleLinkingDoc::Register](#register)|Das Dokument registriert die OLE-System-DLLs.|
|[COleLinkingDoc::Revoke](#revoke)|Hebt die Registrierung des Dokuments ab.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleLinkingDoc::OnFindEmbeddedItem](#onfindembeddeditem)|Sucht das angegebene eingebettete Element.|
|[COleLinkingDoc::OnGetLinkedItem](#ongetlinkeditem)|Sucht das angegebene verknüpfte Element.|

## <a name="remarks"></a>Hinweise

Eine containeranwendung, die unterstützt das verknüpfen, um eingebettete Elemente wird einen "Link-Container" bezeichnet. Die [OCLIENT](../../overview/visual-cpp-samples.md) beispielanwendung ist ein Beispiel für einen Link-Container.

Wenn ein verknüpftes Element-Quelle ein eingebettetes Element in einem anderen Dokument ist, muss das Dokument enthält in der Reihenfolge für das eingebettete Element bearbeitet werden geladen werden. Aus diesem Grund muss ein Link-Container können von einer anderen containeranwendung gestartet werden, wenn der Benutzer die Quelle eines verknüpften Elements bearbeiten möchte. Ihre Anwendung muss auch verwenden, die [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) -Klasse so, dass es Dokumente, die beim Starten von programmgesteuert erstellen kann.

Damit wird Ihren Container einen Link-Container, leiten Sie die Dokumentklasse von `COleLinkingDoc` anstelle von [COleDocument](../../mfc/reference/coledocument-class.md). Wie bei jedem anderen OLE-Container müssen Sie Ihre Klasse zum Speichern von der Anwendung native Daten als auch eingebettete oder verknüpfte Elemente entwerfen. Darüber hinaus müssen Sie Datenstrukturen für das Speichern Ihrer systemeigenen Daten entwerfen. Wenn Sie definieren eine `CDocItem`-abgeleitete Klasse, für die systemeigene der für Ihre Anwendung Daten, Sie können mithilfe der Benutzeroberfläche von definiert `COleDocument` Ihre systemeigenen Daten als auch Ihre OLE-Daten zu speichern.

Deklarieren, damit Ihre Anwendung programmgesteuert durch einen anderen Container gestartet werden kann, eine `COleTemplateServer` -Objekt als Member von Ihrer Anwendungsverzeichnis `CWinApp`-Klasse:

[!code-cpp[NVC_MFCOleContainer#23](../../mfc/codesnippet/cpp/colelinkingdoc-class_1.h)]

In der `InitInstance` Memberfunktion Ihre `CWinApp`-abgeleitete Klasse sein, eine Dokumentvorlage erstellen, und geben Sie Ihre `COleLinkingDoc`-abgeleitete Klasse als Document-Klasse:

[!code-cpp[NVC_MFCOleContainer#24](../../mfc/codesnippet/cpp/colelinkingdoc-class_2.cpp)]

Verbinden Ihrer `COleTemplateServer` Objekt, das Ihren Dokumentvorlagen durch Aufrufen des Objekts `ConnectTemplate` Member-Funktion, und registrieren, die alle-Klasse, die mit dem OLE-System durch Aufrufen von Objekte `COleTemplateServer::RegisterAll`:

[!code-cpp[NVC_MFCOleContainer#25](../../mfc/codesnippet/cpp/colelinkingdoc-class_3.cpp)]

Ein Beispiel für `CWinApp`-Definition der Klasse abgeleitet und `InitInstance` funktionieren, finden Sie unter OCLIENT. H und OCLIENT. CPP im MFC-Beispiel [OCLIENT](../../overview/visual-cpp-samples.md).

Weitere Informationen zur Verwendung von `COleLinkingDoc`, finden Sie in den Artikeln [Container: Implementieren eines Containers](../../mfc/containers-implementing-a-container.md) und [Container: Erweiterte Features](../../mfc/containers-advanced-features.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

`COleLinkingDoc`

## <a name="requirements"></a>Anforderungen

**Header:** afxole.h

##  <a name="colelinkingdoc"></a>  COleLinkingDoc::COleLinkingDoc

Erstellt eine `COleLinkingDoc` Objekt ohne Kommunikation mit dem OLE-System-DLLs ab.

```
COleLinkingDoc();
```

### <a name="remarks"></a>Hinweise

Rufen Sie die `Register` Member-Funktion, um OLE darüber zu informieren, dass das Dokument geöffnet ist.

##  <a name="onfindembeddeditem"></a>  COleLinkingDoc::OnFindEmbeddedItem

Wird aufgerufen, durch das Framework, um festzustellen, ob das Dokument mit eine eingebettete OLE-Element mit dem angegebenen Namen enthält.

```
virtual COleClientItem* OnFindEmbeddedItem(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>Parameter

*lpszItemName*<br/>
Zeiger auf den Namen der eingebetteten OLE-Element angefordert.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das angegebene Element; NULL, wenn das Element nicht gefunden wurde.

### <a name="remarks"></a>Hinweise

Die Standardimplementierung durchsucht die Liste der eingebetteten Elemente für ein Element mit dem angegebenen Namen (der Namensvergleich wird die Groß-/Kleinschreibung beachten). Überschreiben Sie diese Funktion, wenn Sie über eine eigene Methode zum Speichern von oder benennen die eingebettete OLE-Elemente verfügen.

##  <a name="ongetlinkeditem"></a>  COleLinkingDoc::OnGetLinkedItem

Wird aufgerufen, durch das Framework zu überprüfen, ob das Dokument eine Verbindungsserver-Element mit dem angegebenen Namen enthält.

```
virtual COleServerItem* OnGetLinkedItem(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>Parameter

*lpszItemName*<br/>
Zeiger auf den Namen für die verknüpfte OLE-Element angefordert.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das angegebene Element; NULL, wenn das Element nicht gefunden wurde.

### <a name="remarks"></a>Hinweise

Der Standardwert `COleLinkingDoc` Implementierung gibt immer NULL. Diese Funktion ist in der abgeleiteten Klasse überschrieben `COleServerDoc` um die Liste der OLE-Server-Elemente für ein verknüpftes Element mit dem angegebenen Namen zu suchen (der Namensvergleich wird die Groß-/Kleinschreibung beachten). Überschreiben Sie diese Funktion, wenn Sie eine eigene Methode für das Speichern oder Abrufen von Elementen der Verbindungsserver implementiert haben.

##  <a name="register"></a>  COleLinkingDoc::Register

Informiert der OLE-System-DLLs, dass das Dokument geöffnet ist.

```
BOOL Register(
    COleObjectFactory* pFactory,
    LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Parameter

*pFactory*<br/>
Zeiger auf ein OLE-Factory-Objekt (kann NULL sein).

*lpszPathName*<br/>
Zeiger auf den vollqualifizierten Pfad des Containerdokuments.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn das Dokument erfolgreich registriert wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion wird beim Erstellen oder öffnen eine benannte Datei aus, um das Dokument mit dem OLE-System-DLLs zu registrieren. Besteht keine Notwendigkeit, diese Funktion aufzurufen, wenn das Dokument ein eingebettetes Element darstellt.

Bei Verwendung von `COleTemplateServer` in Ihrer Anwendung `Register` heißt für Sie von `COleLinkingDoc`Implementierung von `OnNewDocument`, `OnOpenDocument`, und `OnSaveDocument`.

##  <a name="revoke"></a>  COleLinkingDoc::Revoke

Informiert der OLE-System-DLLs, dass das Dokument nicht mehr geöffnet ist.

```
void Revoke();
```

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, um die Registrierung des Dokuments ab, mit dem OLE-System-DLLs zu widerrufen.

Sie sollten diese Funktion beim Schließen einer benannten Datei aufrufen, aber Sie in der Regel müssen nicht direkt aufgerufen. `Revoke` wird aufgerufen, vom `COleLinkingDoc`Implementierung von `OnCloseDocument`, `OnNewDocument`, `OnOpenDocument`, und `OnSaveDocument`.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[COleDocument-Klasse](../../mfc/reference/coledocument-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)
