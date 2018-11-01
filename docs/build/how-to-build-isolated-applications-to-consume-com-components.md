---
title: 'Gewusst wie: Erstellen von isolierten Anwendungen zur Verwendung von COM-Komponenten'
ms.date: 11/04/2016
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 04587547-1174-44ab-bd99-1292358fba20
ms.openlocfilehash: ba35c016996604e2b433083c2de7b9ddc807d52c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587537"
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