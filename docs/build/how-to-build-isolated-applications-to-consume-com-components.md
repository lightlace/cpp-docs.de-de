---
title: 'Vorgehensweise: Erstellen von isolierten Anwendungen zur COM-Komponenten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 04587547-1174-44ab-bd99-1292358fba20
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d2acabb6a5e9c35029b346097a66eaf1311826c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704027"
---
# <a name="how-to-build-isolated-applications-to-consume-com-components"></a>Gewusst wie: Erstellen von isolierten Anwendungen zur Verwendung von COM-Komponenten

Isolierte Anwendungen sind Anwendungen, die Manifeste, die die Anwendung integriert haben. Sie können die isolierte Anwendungen zur COM-Komponenten erstellen.

### <a name="to-add-com-references-to-manifests-of-isolated-applications"></a>COM-Verweise auf die Manifeste der isolierten Anwendungen hinzufügen

1. Öffnen Sie die Eigenschaftenseiten des Projekts für die isolierte Anwendung.

1. Erweitern Sie die **Konfigurationseigenschaften** Knoten, und erweitern Sie dann die **Manifesttool** Knoten.

1. Wählen Sie die **Isolated COM** Eigenschaftenseite, und legen anschließend die **Komponentendateiname** -Eigenschaft auf den Namen der COM-Komponente, die Sie auf die isolierte Anwendung nutzen möchten.

1. Klicken Sie auf **OK**.

### <a name="to-build-manifests-into-isolated-applications"></a>Manifeste in isolierten Anwendungen zu integrieren.

1. Öffnen Sie die Eigenschaftenseiten des Projekts für die isolierte Anwendung.

1. Erweitern Sie die **Konfigurationseigenschaften** Knoten, und erweitern Sie dann die **Manifesttool** Knoten.

1. Wählen Sie die **ein- und Ausgabe** Eigenschaftenseite, und legen anschließend die **Manifest einbetten** -Eigenschaft **Ja**.

1. Klicken Sie auf **OK**.

1. Erstellen Sie die Projektmappe.

## <a name="see-also"></a>Siehe auch

[Isolierte Anwendungen](/windows/desktop/SbsCs/isolated-applications)<br/>
[Zu Seite-an-Seite-Assemblys](/windows/desktop/SbsCs/about-side-by-side-assemblies-)