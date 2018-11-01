---
title: 'Windows Sockets: Umwandeln von Zeichenfolgen'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], multibyte character string conversion
- sockets [MFC], multibyte character string conversion issues
- string conversion, multibyte character strings
ms.assetid: 9df522b5-6b23-41e0-bb96-e4e623baf141
ms.openlocfilehash: 984554c2405bf6b8ae6a522e545bcbba6ebae529
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543727"
---
# <a name="windows-sockets-converting-strings"></a>Windows Sockets: Umwandeln von Zeichenfolgen

In diesem Artikel und zwei begleitenden Artikel erläutern mehrere Probleme bei der Windows Sockets-Programmierung. Dieser Artikel beschreibt das Konvertieren von Zeichenfolgen. Die anderen Probleme finden Sie im [Windows Sockets: blockieren](../mfc/windows-sockets-blocking.md) und [Windows Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md).

Wenn Sie verwenden, oder leiten Sie von der Klasse [CAsyncSocket](../mfc/reference/casyncsocket-class.md), Sie müssen diese Probleme selbst zu verwalten. Wenn Sie verwenden, oder leiten Sie von der Klasse [CSocket](../mfc/reference/csocket-class.md), MFC für Sie verwaltet.

## <a name="converting-strings"></a>Konvertieren von Zeichenfolgen

Wenn die Kommunikation zwischen Anwendungen, die gespeichert, die in unterschiedlichen Formaten Breitzeichen-Zeichenfolgen verwenden, wie z. B. Unicode- oder multibyte-Zeichensätze (MBCS) legt fest, oder eines der folgenden und einer Anwendung mit ANSI-Zeichenfolgen, müssen Sie die Konvertierungen verwalten. selbst unter `CAsyncSocket`. Die `CArchive` verwendete Objekt eine `CSocket` Objekt verwaltet diese Konvertierung für Sie über die Funktionen der Klasse [CString](../atl-mfc-shared/reference/cstringt-class.md). Weitere Informationen finden Sie in der Windows Sockets-Spezifikation befindet sich im Windows SDK.

Weitere Informationen finden Sie unter:

- [Windows-Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows-Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows-Sockets: Hintergrund](../mfc/windows-sockets-background.md)

- [Windows-Sockets: Blockieren](../mfc/windows-sockets-stream-sockets.md)

- [Windows-Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Siehe auch

[Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)

