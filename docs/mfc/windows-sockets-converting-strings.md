---
title: 'Windows Sockets: Konvertieren von Zeichenfolgen'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], multibyte character string conversion
- sockets [MFC], multibyte character string conversion issues
- string conversion, multibyte character strings
ms.assetid: 9df522b5-6b23-41e0-bb96-e4e623baf141
ms.openlocfilehash: eaf278fc2689f0afa9ab6ff30f1294c36de5d7ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62217390"
---
# <a name="windows-sockets-converting-strings"></a>Windows Sockets: Konvertieren von Zeichenfolgen

In diesem Artikel und zwei begleitenden Artikel erläutern mehrere Probleme bei der Windows Sockets-Programmierung. Dieser Artikel beschreibt das Konvertieren von Zeichenfolgen. Die anderen Probleme finden Sie im [Windows Sockets: Blockierende](../mfc/windows-sockets-blocking.md) und [Windows Sockets: Die Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md).

Wenn Sie verwenden, oder leiten Sie von der Klasse [CAsyncSocket](../mfc/reference/casyncsocket-class.md), Sie müssen diese Probleme selbst zu verwalten. Wenn Sie verwenden, oder leiten Sie von der Klasse [CSocket](../mfc/reference/csocket-class.md), MFC für Sie verwaltet.

## <a name="converting-strings"></a>Konvertieren von Zeichenfolgen

Wenn die Kommunikation zwischen Anwendungen, die gespeichert, die in unterschiedlichen Formaten Breitzeichen-Zeichenfolgen verwenden, wie z. B. Unicode- oder multibyte-Zeichensätze (MBCS) legt fest, oder eines der folgenden und einer Anwendung mit ANSI-Zeichenfolgen, müssen Sie die Konvertierungen verwalten. selbst unter `CAsyncSocket`. Die `CArchive` verwendete Objekt eine `CSocket` Objekt verwaltet diese Konvertierung für Sie über die Funktionen der Klasse [CString](../atl-mfc-shared/reference/cstringt-class.md). Weitere Informationen finden Sie in der Windows Sockets-Spezifikation befindet sich im Windows SDK.

Weitere Informationen finden Sie unter:

- [Windows-Sockets: Verwenden der Klasse „CAsyncSocket“](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows-Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows-Sockets: Hintergrund](../mfc/windows-sockets-background.md)

- [Windows-Sockets: Streamsockets](../mfc/windows-sockets-stream-sockets.md)

- [Windows-Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Siehe auch

[Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)
