---
title: Schließen von Dateien
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
ms.openlocfilehash: 69a0960c1edabab00cb71702acda526ee9ebd798
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267055"
---
# <a name="closing-files"></a>Schließen von Dateien

Wie gewohnt in e/a-Vorgängen, müssen wenn Sie fertig, eine Datei sind, Sie ihn schließen.

#### <a name="to-close-a-file"></a>Um eine Datei zu schließen.

1. Verwenden der **schließen** Member-Funktion. Diese Funktion schließt die Dateisystem-Datei und leert Puffer bei Bedarf.

Wenn Sie zugeordnet der [CFile](../mfc/reference/cfile-class.md) der Frame-Objekt (wie in dem Beispiel in [Öffnen von Dateien](../mfc/opening-files.md)), das Objekt wird automatisch geschlossen und dann zerstört, wenn sie den Gültigkeitsbereich verlässt. Beachten Sie, dass beim Löschen der `CFile` Objekt der physische Datei im Dateisystem wird nicht gelöscht werden.

## <a name="see-also"></a>Siehe auch

[Dateien](../mfc/files-in-mfc.md)
