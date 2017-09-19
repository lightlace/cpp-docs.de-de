---
title: CSocketFile Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSocketFile
- AFXSOCK/CSocketFile
- AFXSOCK/CSocketFile::CSocketFile
dev_langs:
- C++
helpviewer_keywords:
- networks [C++], archive
- serialization [C++], network
- networks [C++], serializing to
- CSocketFile class
- archives [C++], network
- SOCKET handle
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
caps.latest.revision: 24
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 6ca331c07e0a9fc48f152042fcccd5c38e743ccf
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="csocketfile-class"></a>CSocketFile-Klasse
Ein `CFile` -Objekt zum Senden und Empfangen von Daten in einem Netzwerk über Windows Sockets.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSocketFile : public CFile  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSocketFile::CSocketFile](#csocketfile)|Erstellt ein `CSocketFile`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Sie anfügen können die `CSocketFile` -Objekt an eine `CSocket` Objekt für diesen Zweck. Außerdem können und in der Regel, fügen Sie der `CSocketFile` -Objekt ein `CArchive` Objekt vereinfachen das Senden und Empfangen von Daten mithilfe von MFC-Serialisierung.  
  
 Zum Serialisieren von Daten (senden) Sie fügen Sie es in das Archiv, der aufgerufen wird, `CSocketFile` Memberfunktionen zum Schreiben von Daten an die `CSocket` Objekt. Zum Deserialisieren (empfangen) Daten, die Sie aus dem Archiv extrahieren. Dies bewirkt, dass das Archiv Aufrufen `CSocketFile` Memberfunktionen zum Lesen von Daten aus der `CSocket` Objekt.  
  
> [!TIP]
>  Neben der Verwendung von `CSocketFile` wie hier beschrieben, können Sie sie als eigenständige Datei-Objekt, wie Sie mit `CFile`, seiner Basisklasse. Sie können auch `CSocketFile` mit Funktionen Archiv basierende MFC-Serialisierung. Da `CSocketFile` unterstützen nicht alle `CFile`der Funktionalität, einige Standard MFC serialisieren Funktionen sind nicht kompatibel mit `CSocketFile`. Dies gilt insbesondere für die `CEditView` Klasse. Sollten Sie nicht versuchen, serialisieren `CEditView` Daten über eine `CArchive` Objekt angefügt, um eine `CSocketFile` -Objekt mit `CEditView::SerializeRaw`; verwenden **CEditView:: Serialize** stattdessen. Die `SerializeRaw` erwartet das File-Objekt, um Funktionen, z. B. `Seek`, `CSocketFile` keinen.  
  
 Bei Verwendung `CArchive` mit `CSocketFile` und `CSocket`, treten möglicherweise Situationen, in denen **CSocket::Receive** tritt in eine Schleife (durch **PumpMessages(FD_READ)**) warten, bis die angeforderte Anzahl der Bytes. Dies ist, da die Windows-Sockets nur ein Aufruf von empfangen pro Benachrichtigung FD_READ maskiert, ermöglichen jedoch `CSocketFile` und `CSocket` mehrere Recv-Aufrufe pro FD_READ maskiert zulassen. Wenn Sie eine FD_READ maskiert erhalten, wenn keine Daten lesen, stürzt die Anwendung. Wenn Sie einen anderen FD_READ maskiert nie erhalten, reagiert die Anwendung die Kommunikation über den Socket.  
  
 Sie können dieses Problem folgendermaßen beheben. In der `OnReceive` Methode der Socketklasse Aufruf **CAsyncSocket::IOCtl (FIONREAD,...) ** vor dem Aufrufen der `Serialize` -Methode Ihrer Nachrichtenklasse, wenn die erwarteten Daten in den Socket gelesen werden, die Größe des TCP-Pakets (maximale Übertragungseinheit der Netzwerk-Mittel in der Regel mit der mindestens 1096 Bytes) überschreitet. Wenn die Größe der verfügbaren Daten kleiner als erforderlich ist, warten Sie alle Daten empfangen werden und nur dann lesen.  
  
 Im folgenden Beispiel `m_dwExpected` ist die ungefähre Anzahl von Bytes, die der Benutzer erwartet, empfangen. Es wird vorausgesetzt, dass Sie an anderer Stelle im Code deklariert werden.  
  
 [!code-cpp[NVC_MFCSocketThread&4;](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]  
  
 Weitere Informationen finden Sie unter [Windows-Sockets in MFC](../../mfc/windows-sockets-in-mfc.md), [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md), als auch [API von Windows Sockets 2](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CSocketFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Datei afxsock.h  
  
##  <a name="csocketfile"></a>CSocketFile::CSocketFile  
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
 Gibt an, ob das File-Objekt für die Verwendung mit einem `CArchive` Objekt. Übergeben Sie **FALSE** nur, wenn Sie verwenden möchten die `CSocketFile` -Objekt als eigenständigen Parser, wie Sie eine eigenständige `CFile` Objekt mit bestimmten Einschränkungen. Dieses Flag wird wie die `CArchive` Objekt angefügt, um die `CSocketFile` Objekt verwaltet den Puffer zum Lesen.  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor des Objekts trennt sich vom Socketobjekt, wenn das Objekt den Gültigkeitsbereich verlässt oder gelöscht wird.  
  
> [!NOTE]
>  Ein `CSocketFile` kann auch verwendet werden, als (begrenzte) Datei ohne ein `CArchive` Objekt. In der Standardeinstellung die `CSocketFile` des Konstruktors `bArchiveCompatible` Parameter ist **TRUE**. Dies gibt an, dass das Objekt für die Verwendung mit einem Archiv ist. Um das Dateiobjekt ohne Archiv zu verwenden, übergeben **FALSE** in der `bArchiveCompatible` Parameter.  
  
 Im Modus "Archiv kompatibel" ein `CSocketFile` Objekt bietet eine bessere Leistung und reduziert die Gefahr von "Deadlocks". Ein Deadlock tritt auf, wenn die sendenden und empfangenden Sockets voneinander oder für eine gemeinsame Ressource warten. Diese Situation kann eintreten, wenn die `CArchive` -Objekt verwendet wird, mit der `CSocketFile` Weise mit einer `CFile` Objekt. Mit `CFile`, das Archiv kann davon ausgehen, dass wenn weniger Bytes als angefordert empfangen, die das Ende der Datei erreicht wurde.  
  
 Mit `CSocketFile`, jedoch Daten basiert auf Nachrichten; der Puffer kann mehrere Nachrichten enthalten, Empfangen von weniger als die Anzahl der angeforderten Bytes, so bedeutet das nicht Ende der Datei. Die Anwendung wird nicht in diesem Fall blockiert, wie sie mit `CFile`, und sie können weiterhin Nachrichten aus dem Puffer zu lesen, bis der Puffer leer ist. Die [CArchive::IsBufferEmpty](../../mfc/reference/carchive-class.md#isbufferempty) Funktion ist nützlich für das Überwachen des Status des Archivs Puffer in einem solchen Fall.  
  
 Weitere Informationen zum Verwenden von `CSocketFile`, finden Sie in den Artikeln [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md) und [Windows Sockets: Beispiel für Sockets mithilfe von Archiven](../../mfc/windows-sockets-example-of-sockets-using-archives.md).  
  
## <a name="see-also"></a>Siehe auch  
 [CFile-Klasse](../../mfc/reference/cfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket-Klasse](../../mfc/reference/casyncsocket-class.md)   
 [CSocket-Klasse](../../mfc/reference/csocket-class.md)

