---
title: 'Windows Sockets: Umwandeln von Zeichenfolgen | Microsoft-Dokumentation'
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
ms.openlocfilehash: 6b23d2149659cdad320a58bdff0f42ba113b5696
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378935"
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

