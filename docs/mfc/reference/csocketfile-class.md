---
title: CSocketFile-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: c4c74d1ab89c45b7871cf0b4fa0d8a6350bc1425
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43209636"
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
 Sie anfügen können die `CSocketFile` -Objekt an eine `CSocket` Objekt für diesen Zweck. Sie können auch und in der Regel wirken, fügen Sie an der `CSocketFile` -Objekt eine `CArchive` Objekt, das vereinfachen das Senden und Empfangen von Daten mithilfe von MFC-Serialisierung.  
  
 Zum Serialisieren von Daten (senden), Sie fügen Sie es in das Archiv, das aufruft, `CSocketFile` Memberfunktionen zum Schreiben von Daten, die `CSocket` Objekt. Beim Deserialisieren (empfangen) Daten, die Sie aus dem Archiv extrahieren. Dies bewirkt, dass das Archiv Aufrufen `CSocketFile` Memberfunktionen zum Lesen von Daten aus der `CSocket` Objekt.  
  
> [!TIP]
>  Neben der Verwendung von `CSocketFile` wie hier beschrieben, können Sie sie als eigenständige Datei-Objekt, ebenso wie mit `CFile`, seiner Basisklasse. Sie können auch `CSocketFile` mit alle Funktionen der Archiv-basierte MFC-Serialisierung. Da `CSocketFile` unterstützt nicht alle `CFile`Serialisieren der Funktionalität, einen Standard-MFC die Funktionen sind nicht kompatibel mit `CSocketFile`. Dies gilt insbesondere für die `CEditView` Klasse. Sie sollten nicht versuchen, serialisieren `CEditView` Daten über eine `CArchive` Objekt angefügt, um eine `CSocketFile` -Objekt mit `CEditView::SerializeRaw`; verwenden `CEditView::Serialize` stattdessen. Die `SerializeRaw` erwartet das Dateiobjekt, wenn Funktionen wie `Seek`, `CSocketFile` verfügt nicht über.  
  
 Bei Verwendung von `CArchive` mit `CSocketFile` und `CSocket`, treten möglicherweise eine Situation, in denen `CSocket::Receive` tritt in eine Schleife (von `PumpMessages(FD_READ)`) warten auf die angeforderte Anzahl der Bytes. Dies ist, da Windows Sockets nur ein empfangener Aufruf pro FD_READ maskiert-Benachrichtigung, ermöglichen aber `CSocketFile` und `CSocket` mehrere empfangener Anrufe pro FD_READ maskiert zulassen. Wenn Sie eine FD_READ maskiert erhalten, wenn keine Daten lesen, hängt die Anwendung. Wenn Sie einen anderen FD_READ maskiert nie erhalten haben, reagiert die Anwendung die Kommunikation über den Socket.  
  
 Sie können dieses Problem wie folgt beheben. In der `OnReceive` -Methode der Socket-Klasse, Aufruf `CAsyncSocket::IOCtl(FIONREAD, ...)` vor dem Aufruf der `Serialize` Methode Ihrer Message-Klasse, wenn die erwarteten Daten vom Socket gelesen werden, die Größe des TCP-Pakets (maximale Übertragungseinheit des Mediums Netzwerk überschreitet in der Regel mit der mindestens 1096 Bytes). Wenn die Größe der verfügbaren Daten kleiner als erforderlich ist, warten Sie alle Daten empfangen werden und erst dann damit den Lesevorgang beginnt.  
  
 Im folgenden Beispiel `m_dwExpected` wird die ungefähre Anzahl von Bytes, die der Benutzer zu empfangen erwartet. Es wird vorausgesetzt, dass Sie sie an anderer Stelle in Ihrem Code deklarieren.  
  
 [!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]  
  
 Weitere Informationen finden Sie unter [Windows-Sockets in MFC](../../mfc/windows-sockets-in-mfc.md), [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md), als auch [Windows Sockets-2-API](/windows/desktop/WinSock/windows-sockets-start-page-2).  
  
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
 *pSocket*  
 Der Socket, auf das Anfügen an die `CSocketFile` Objekt.  
  
 *bArchiveCompatible*  
 Gibt an, ob das Objekt "Datei" für die Verwendung mit einem `CArchive` Objekt. Übergeben Sie FALSE nur, wenn Sie verwenden möchten die `CSocketFile` Objekt als eigenständigen Parser, wie Sie eine eigenständige `CFile` Objekt mit bestimmten Einschränkungen. Dieses Flag ändert wie der `CArchive` Objekt angefügt, um die `CSocketFile` Objekt verwaltet den Puffer zum Lesen.  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor trennt selbst von das Socketobjekt, wenn das Objekt den Gültigkeitsbereich verlässt oder gelöscht wird.  
  
> [!NOTE]
>  Ein `CSocketFile` kann auch verwendet werden, als (begrenzt) Datei ohne eine `CArchive` Objekt. In der Standardeinstellung die `CSocketFile` des Konstruktors *bArchiveCompatible* Parameter TRUE ist. Dies gibt an, dass das Objekt "Datei" für die Verwendung mit einem Archiv. Um das Objekt "Datei" ohne ein Archiv zu verwenden, übergeben Sie "false", in der *bArchiveCompatible* Parameter.  
  
 In den Modus "Archive-Compatible" ein `CSocketFile` Objekt bietet eine bessere Leistung und reduziert die Gefahr von "Deadlock". Ein Deadlock tritt auf, wenn die sendenden und empfangenden Sockets voneinander oder für eine gemeinsame Ressource warten. Diese Situation kann eintreten, wenn die `CArchive` Objekt hat die `CSocketFile` die Möglichkeit, dies der Fall ist mit, einem `CFile` Objekt. Mit `CFile`, das Archiv kann davon ausgehen, empfängt er weniger Bytes als angefordert, am Ende der Datei erreicht wurde.  
  
 Mit `CSocketFile`, jedoch Daten basiert auf Nachrichten; der Puffer kann mehrere Nachrichten enthalten, erhalten also weniger als die Anzahl der angeforderten Bytes Ende der Datei nicht impliziert. Die Anwendung wird in diesem Fall nicht blockiert, wie sie mit `CFile`, und sie können fortfahren, Lesen von Nachrichten aus dem Puffer, bis der Puffer leer ist. Die [CArchive::IsBufferEmpty](../../mfc/reference/carchive-class.md#isbufferempty) Funktion ist nützlich für das Überwachen des Status des Archivs Puffer in einem solchen Fall.  
  
 Weitere Informationen zur Verwendung von `CSocketFile`, finden Sie in den Artikeln [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md) und [Windows Sockets: Beispiel für Sockets mithilfe von Archive](../../mfc/windows-sockets-example-of-sockets-using-archives.md).  
  
## <a name="see-also"></a>Siehe auch  
 [CFile-Klasse](../../mfc/reference/cfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket-Klasse](../../mfc/reference/casyncsocket-class.md)   
 [CSocket-Klasse](../../mfc/reference/csocket-class.md)
