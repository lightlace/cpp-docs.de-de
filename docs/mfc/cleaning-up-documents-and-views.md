---
title: Bereinigen von Dokumenten und Ansichten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f4325b0de10861fc76ee9ab816376f40ba0ba587
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437416"
---
# <a name="cleaning-up-documents-and-views"></a>Bereinigen von Dokumenten und Ansichten

Wenn ein Dokument geschlossen wird, ruft das Framework zuerst seine [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) Member-Funktion. Wenn Sie im Verlauf des Vorgangs des Dokuments, auf dem Heap Arbeitsspeicher zugeordnet `DeleteContents` ist der beste Ort für die Zuordnung aufheben.

> [!NOTE]
>  Sie sollten nicht die Dokumentendaten in der Destruktor des Dokuments Zuordnung aufheben. Im Fall einer SDI-Anwendung kann das Document-Objekt wiederverwendet werden.

Sie können eine Ansicht des-Destruktor, um den Arbeitsspeicher freigeben, die, den Sie auf dem Heap reserviert, überschreiben.

## <a name="see-also"></a>Siehe auch

[Initialisieren und Bereinigen von Dokumenten und Ansichten](../mfc/initializing-and-cleaning-up-documents-and-views.md)

