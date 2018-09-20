---
title: Schließen von Dateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c392ef728e1d796a02cfa32edc2c3e8c74d083b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426236"
---
# <a name="closing-files"></a>Schließen von Dateien

Wie gewohnt in e/a-Vorgängen, müssen wenn Sie fertig, eine Datei sind, Sie ihn schließen.

#### <a name="to-close-a-file"></a>Um eine Datei zu schließen.

1. Verwenden der **schließen** Member-Funktion. Diese Funktion schließt die Dateisystem-Datei und leert Puffer bei Bedarf.

Wenn Sie zugeordnet der [CFile](../mfc/reference/cfile-class.md) der Frame-Objekt (wie in dem Beispiel in [Öffnen von Dateien](../mfc/opening-files.md)), das Objekt wird automatisch geschlossen und dann zerstört, wenn sie den Gültigkeitsbereich verlässt. Beachten Sie, dass beim Löschen der `CFile` Objekt der physische Datei im Dateisystem wird nicht gelöscht werden.

## <a name="see-also"></a>Siehe auch

[Dateien](../mfc/files-in-mfc.md)

