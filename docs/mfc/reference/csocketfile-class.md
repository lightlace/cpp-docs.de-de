---
title: CSocketFile Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSocketFile
- AFXSOCK/CSocketFile
- AFXSOCK/CSocketFile::CSocketFile
dev_langs:
- C++
helpviewer_keywords:
- CSocketFile [MFC], CSocketFile
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0e3bf8d9ee58143e7a96b85174e4533b3c2e50ec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
 Sie anfügen können die `CSocketFile` -Objekt an eine `CSocket` Objekt für diesen Zweck. Auch können und in der Regel fügen Sie hierzu die `CSocketFile` -Objekt an eine `CArchive` zu vereinfachen das Senden und Empfangen von Daten mithilfe der Serialisierung von MFC-Objekt.  
  
 Um (senden) von Daten zu serialisieren, Sie fügen Sie es in das Archiv, der aufgerufen wird, `CSocketFile` Memberfunktionen zum Schreiben von Daten an die `CSocket` Objekt. Beim Deserialisieren (empfangen) Sie extrahieren Daten aus dem Archiv. Dies bewirkt, dass das Archiv Aufrufen `CSocketFile` Memberfunktionen zum Lesen von Daten aus der `CSocket` Objekt.  
  
> [!TIP]
>  Neben der Verwendung von `CSocketFile` wie hier beschrieben, können Sie sie als eigenständige Datei-Objekt, ebenso wie Sie mit `CFile`, seine Basisklasse. Sie können auch `CSocketFile` mit Funktionen Archiv basierende MFC-Serialisierung. Da `CSocketFile` unterstützen nicht alle `CFile`der Funktionalität, einige Standard-MFC serialisieren Funktionen sind nicht kompatibel mit `CSocketFile`. Dies gilt insbesondere für die `CEditView` Klasse. Sie sollten nicht versuchen, serialisieren `CEditView` Daten über eine `CArchive` Objekt angefügt, um eine `CSocketFile` -Objekt unter Verwendung `CEditView::SerializeRaw`; verwenden **CEditView:: Serialize** stattdessen. Die `SerializeRaw` erwartet das Objekt "Datei", haben die Funktionen, z. B. `Seek`, `CSocketFile` verfügt nicht über.  
  
 Bei Verwendung von `CArchive` mit `CSocketFile` und `CSocket`, eine Situation auftreten, in denen **CSocket::Receive** geht in einer Schleife (durch **PumpMessages(FD_READ)**) warten auf die angeforderte Menge von Bytes. Dies ist, da die Windows-Sockets nur ein Aufruf von Recv pro FD_READ maskiert Benachrichtigung, können aber `CSocketFile` und `CSocket` können mehrere Recv Aufrufe pro FD_READ maskiert. Wenn Sie eine FD_READ maskiert erhalten, wenn keine Daten lesen, stürzt die Anwendung. Wenn Sie einen anderen FD_READ maskiert nie erhalten, reagiert die Anwendung die Kommunikation über den Socket.  
  
 Sie können dieses Problem wie folgt beheben. In der `OnReceive` Methode der Socket-Klasse, Aufruf **CAsyncSocket::IOCtl (FIONREAD,...)**  vor dem Aufruf der `Serialize` Methode von der Message-Klasse, wenn die erwarteten Daten aus den Socket gelesen werden, die Größe des TCP-Pakets (maximale Übertragungseinheit der Network "Mittel", in der Regel mit der mindestens 1096 Bytes) überschreitet. Wenn die Größe der verfügbaren Daten kleiner als erforderlich ist, warten Sie alle Daten empfangen werden und nur den Lesevorgang starten.  
  
 Im folgenden Beispiel `m_dwExpected` die ungefähre Anzahl von Bytes, die vom Benutzer erwarteten empfangen wird. Es wird vorausgesetzt, dass Sie an anderer Stelle im Code deklariert werden.  
  
 [!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]  
  
 Weitere Informationen finden Sie unter [Windows-Sockets in MFC](../../mfc/windows-sockets-in-mfc.md), [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md), als auch [Windows Sockets-2-API](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CSocketFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Datei afxsock.h  
  
##  <a name="csocketfile"></a>  CSocketFile::CSocketFile  
 Erstellt ein `CSocketFile`-Objekt.  
  
```  
explicit CSocketFile(
    CSocket* pSocket,  
    BOOL bArchiveCompatible = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pSocket`  
 Der Socket an den `CSocketFile` Objekt.  
  
 `bArchiveCompatible`  
 Gibt an, ob das Objekt "Datei" für die Verwendung mit einem `CArchive` Objekt. Übergeben Sie **"false"** nur, wenn Sie verwenden möchten die `CSocketFile` Objekt in einer eigenständigen Weise, wie Sie eine eigenständige `CFile` Objekt, mit bestimmten Einschränkungen. Dieses Flag wird wie die `CArchive` Objekt angefügt, um die `CSocketFile` Objekt verwaltet den Puffer zum Lesen.  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor des Objekts trennt selbst aus der Socketobjekt, wenn das Objekt den Gültigkeitsbereich verlässt oder gelöscht wird.  
  
> [!NOTE]
>  Ein `CSocketFile` kann auch verwendet werden, als (begrenzt)-Datei ohne eine `CArchive` Objekt. Wird standardmäßig die `CSocketFile` des Konstruktors `bArchiveCompatible` Parameter ist **"true"**. Dies gibt an, dass das Objekt "Datei" für die Verwendung mit einem Archiv. Um das Objekt "Datei" ohne ein Archiv zu verwenden, übergeben **"false"** in der `bArchiveCompatible` Parameter.  
  
 Im Modus "Archiv Compatible" ein `CSocketFile` Objekt bietet eine bessere Leistung und reduziert die Gefahr eines "Deadlocks". Ein Deadlock tritt auf, wenn die sendenden und empfangenden Sockets voneinander oder für eine allgemeine Ressource warten. Diese Situation kann auftreten, wenn die `CArchive` Objekt arbeitet mit der `CSocketFile` Weise mit einem `CFile` Objekt. Mit `CFile`, das Archiv kann davon ausgehen, dass weniger Bytes als angefordert Empfang, die das Ende der Datei erreicht wurde.  
  
 Mit `CSocketFile`jedoch Daten nachrichtenbasiert; der Puffer kann mehrere Nachrichten enthalten, wird daher empfangen von weniger als die Anzahl der angeforderten Bytes Dateiende nicht impliziert. Die Anwendung wird in diesem Fall nicht blockiert, wie mit möglicherweise `CFile`, und sie können weiterhin Nachrichten aus dem Puffer zu lesen, bis der Puffer leer ist. Die [CArchive::IsBufferEmpty](../../mfc/reference/carchive-class.md#isbufferempty) Funktion eignet sich zum Überwachen des Status des Archivs Puffer in einem solchen Fall.  
  
 Weitere Informationen zur Verwendung von `CSocketFile`, finden Sie in den Artikeln [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md) und [Windows Sockets: Beispiel für Sockets mithilfe von Archiven](../../mfc/windows-sockets-example-of-sockets-using-archives.md).  
  
## <a name="see-also"></a>Siehe auch  
 [CFile-Klasse](../../mfc/reference/cfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket-Klasse](../../mfc/reference/casyncsocket-class.md)   
 [CSocket-Klasse](../../mfc/reference/csocket-class.md)
