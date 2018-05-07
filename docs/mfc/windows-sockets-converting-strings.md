---
title: 'Windows Sockets: Umwandeln von Zeichenfolgen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], multibyte character string conversion
- sockets [MFC], multibyte character string conversion issues
- string conversion, multibyte character strings
ms.assetid: 9df522b5-6b23-41e0-bb96-e4e623baf141
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bad57be68ce716cddf2ce44f12e94c545a7bbfd6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="windows-sockets-converting-strings"></a>Windows Sockets: Umwandeln von Zeichenfolgen
In diesem Artikel sowie zwei Begleit-Artikel wird erläutert, mehrere Probleme bei der Windows Sockets-Programmierung. Dieser Artikel behandelt das Konvertieren von Zeichenfolgen. Die anderen Probleme werden behandelt, [Windows Sockets: blockieren](../mfc/windows-sockets-blocking.md) und [Windows Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md).  
  
 Wenn Sie verwenden oder eine von der Klasse Ableitung [CAsyncSocket](../mfc/reference/casyncsocket-class.md), müssen Sie diese Probleme selbst verwalten. Wenn Sie verwenden oder eine von der Klasse Ableitung [CSocket](../mfc/reference/csocket-class.md), MFC für Sie verwaltet.  
  
## <a name="converting-strings"></a>Konvertieren von Zeichenfolgen  
 Wenn Sie die Kommunikation zwischen Anwendungen, die in unterschiedlichen Breitzeichen-Formaten gespeichert unstrukturierte Zeichenfolgen verwenden, z. B. Unicode- oder Mehrbyte-Zeichensätzen (MBCS) legt fest, oder eine der folgenden und einer Anwendung mit ANSI-Zeichenfolgen, müssen Sie die Konvertierungen verwalten. selbst unter `CAsyncSocket`. Die `CArchive` verwendete Objekt eine `CSocket` Objekt verwaltet diese Konvertierung für Sie über die Funktionen der Klasse [CString](../atl-mfc-shared/reference/cstringt-class.md). Weitere Informationen finden Sie in der Windows Sockets-Spezifikation befindet sich im Windows SDK.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Windows-Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows-Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows-Sockets: Hintergrund](../mfc/windows-sockets-background.md)  
  
-   [Windows-Sockets: Blockieren](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows-Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)

