---
title: CSocketFile-Klasse
ms.date: 11/04/2016
f1_keywords:
- CSocketFile
- AFXSOCK/CSocketFile
- AFXSOCK/CSocketFile::CSocketFile
helpviewer_keywords:
- CSocketFile [MFC], CSocketFile
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
ms.openlocfilehash: 3b969f81c0c6e1868a66aeaa1c4d9339792062df
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502449"
---
# <a name="csocketfile-class"></a>CSocketFile-Klasse

Ein `CFile` -Objekt zum Senden und Empfangen von Daten in einem Netzwerk über Windows Sockets.

## <a name="syntax"></a>Syntax

```
class CSocketFile : public CFile
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSocketFile::CSocketFile](#csocketfile)|Erstellt ein `CSocketFile`-Objekt.|

## <a name="remarks"></a>Hinweise

Sie können das `CSocketFile` Objekt zu diesem Zweck `CSocket` an ein-Objekt anfügen. Sie können das Objekt auch in der Regel an ein `CSocketFile` `CArchive` -Objekt anfügen, um das Senden und empfangen von Daten mithilfe der MFC-Serialisierung zu vereinfachen.

Zum Serialisieren (senden) von Daten fügen Sie Sie in das Archiv ein, das `CSocketFile` Member-Funktionen aufruft, um Daten `CSocket` in das-Objekt zu schreiben. Zum Deserialisieren (empfangen) von Daten extrahieren Sie aus dem Archiv. Dies bewirkt, dass das Archiv `CSocketFile` Member-Funktionen aufruft, um Daten `CSocket` aus dem-Objekt zu lesen.

> [!TIP]
>  Neben der `CSocketFile` Verwendung von, wie hier beschrieben, können Sie es als eigenständiges Datei Objekt verwenden, ebenso wie mit `CFile`seiner Basisklasse. Sie können auch mit `CSocketFile` allen Archiv basierten MFC-Serialisierungsfunktionen verwenden. Da `CSocketFile` nicht alle Funktionen von `CFile`unterstützt, sind einige standardmäßige MFC-Serialisierungsfunktionen mit `CSocketFile`nicht kompatibel. Dies gilt insbesondere für die `CEditView` -Klasse. Sie sollten nicht versuchen, Daten durch `CEditView` ein `CArchive` -Objekt zu serialisieren, `CSocketFile` das mit `CEditView::SerializeRaw`einem- `CEditView::Serialize` Objekt verbunden ist. verwenden Sie stattdessen. Die `SerializeRaw` -Funktion erwartet, dass `CSocketFile` das File-Objekt über Funktionen `Seek`verfügt, z. b., die nicht über verfügen.

Wenn Sie mit `CArchive` `CSocketFile` `CSocket::Receive` und `CSocket`verwenden, tritt möglicherweise eine Situation auf, in der eine Schleife `PumpMessages(FD_READ)`(von) in eine Schleife wechselt, die auf die angeforderte Byte Menge wartet. Dies liegt daran, dass Windows Sockets nur einen empfangener-Aufruf pro FD_READ- `CSocketFile` Benachrichtigung `CSocket` zulässt, aber mehrere empfangener-Aufrufe pro FD_READ zulässt. Wenn Sie einen FD_READ erhalten, wenn keine zu lesenden Daten vorhanden sind, ist die Anwendung nicht mehr vorhanden. Wenn Sie nie ein weiteres FD_READ erhalten, hält die Anwendung die Kommunikation über den Socket an.

Sie können dieses Problem wie folgt beheben. In der `OnReceive` -Methode der Socket-Klasse wird `CAsyncSocket::IOCtl(FIONREAD, ...)` aufgerufen, bevor Sie `Serialize` die-Methode der Message-Klasse aufzurufen, wenn die erwarteten Daten, die vom Socket gelesen werden sollen, die Größe eines TCP-Pakets überschreiten (maximale Übertragungseinheit des Netzwerk Mediums). , normalerweise mindestens 1096 Bytes). Wenn die Größe der verfügbaren Daten geringer als benötigt ist, warten Sie, bis alle Daten empfangen wurden, und starten Sie dann den Lesevorgang.

Im folgenden Beispiel `m_dwExpected` gibt die ungefähre Anzahl von Bytes an, die der Benutzer erwartet. Es wird davon ausgegangen, dass Sie es an anderer Stelle im Code deklarieren.

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]

Weitere Informationen finden Sie unter [Windows Sockets in MFC](../../mfc/windows-sockets-in-mfc.md), [Windows Sockets: Verwenden von Sockets mit](../../mfc/windows-sockets-using-sockets-with-archives.md)Archiven und der [Windows Sockets 2-API](/windows/win32/WinSock/windows-sockets-start-page-2).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CSocketFile`

## <a name="requirements"></a>Anforderungen

**Header:** AfxSock. h

##  <a name="csocketfile"></a>CSocketFile:: CSocketFile

Erstellt ein `CSocketFile`-Objekt.

```
explicit CSocketFile(
    CSocket* pSocket,
    BOOL bArchiveCompatible = TRUE);
```

### <a name="parameters"></a>Parameter

*pSocket*<br/>
Der an das `CSocketFile` -Objekt anzufügende Socket.

*bArchiveCompatible*<br/>
Gibt an, ob das Datei Objekt für die Verwendung `CArchive` mit einem-Objekt verwendet werden soll. Übergeben Sie false nur dann, wenn Sie das `CSocketFile` Objekt auf eine eigenständige Weise wie ein eigenständiges `CFile` Objekt mit bestimmten Einschränkungen verwenden möchten. Dieses Flag ändert, wie `CArchive` das Objekt, das `CSocketFile` dem Objekt zugeordnet ist, seinen Puffer zum Lesen verwaltet.

### <a name="remarks"></a>Hinweise

Der Dekonstruktor des Objekts trennt sich von dem Socketobjekt, wenn das Objekt den Gültigkeitsbereich verlässt oder gelöscht wird.

> [!NOTE]
>  Ein `CSocketFile` - `CArchive` Objekt kann auch als (begrenzte) Datei ohne-Objekt verwendet werden. Standardmäßig ist der `CSocketFile` *bArchiveCompatible* -Parameter des Konstruktors true. Dies gibt an, dass das File-Objekt für die Verwendung mit einem Archiv verwendet werden soll. Um das File-Objekt ohne Archive zu verwenden, übergeben Sie false im *bArchiveCompatible* -Parameter.

Im Modus "Archiv kompatibel" bietet ein- `CSocketFile` Objekt eine bessere Leistung und verringert die Gefahr eines "Deadlocks". Ein Deadlock tritt auf, wenn die sendenden und empfangenden Sockets aufeinander oder für eine gemeinsame Ressource warten. Diese Situation kann auftreten, wenn `CArchive` das Objekt `CSocketFile` mit der Art und Weise funktioniert, wie `CFile` es mit einem-Objekt funktioniert. Bei `CFile`kann das Archiv davon ausgehen, dass das Ende der Datei erreicht ist, wenn es weniger Bytes empfängt als angefordert.

Bei `CSocketFile`sind die Daten jedoch Nachrichten basiert. der Puffer kann mehrere Nachrichten enthalten, sodass der Empfangs Wert weniger als die Anzahl der angeforderten Bytes das Ende der Datei nicht impliziert. Die Anwendung wird in diesem Fall in diesem Fall `CFile`nicht blockiert, und Sie kann das Lesen von Nachrichten aus dem Puffer fortsetzen, bis der Puffer leer ist. Die [CArchive:: IsBufferEmpty](../../mfc/reference/carchive-class.md#isbufferempty) -Funktion eignet sich für die Überwachung des Status des Archiv Puffers in einem solchen Fall.

Weitere Informationen zur Verwendung von `CSocketFile`finden Sie in den Artikeln [Windows Sockets: Verwenden von Sockets mit](../../mfc/windows-sockets-using-sockets-with-archives.md) Archiven [und Windows Sockets: Beispiel für Sockets mithilfe von](../../mfc/windows-sockets-example-of-sockets-using-archives.md)Archiven.

## <a name="see-also"></a>Siehe auch

[CFile-Klasse](../../mfc/reference/cfile-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CAsyncSocket-Klasse](../../mfc/reference/casyncsocket-class.md)<br/>
[CSocket-Klasse](../../mfc/reference/csocket-class.md)
