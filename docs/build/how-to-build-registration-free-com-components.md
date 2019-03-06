---
title: 'Vorgehensweise: Erstellen Sie die Registrierung von COM-Komponenten'
ms.date: 11/04/2016
helpviewer_keywords:
- COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
ms.openlocfilehash: 503c3e4399359d793ce660f36844d2edc6602146
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57416769"
---
# <a name="how-to-build-registration-free-com-components"></a>Vorgehensweise: Erstellen Sie die Registrierung von COM-Komponenten

COM-Komponenten ohne Registrierung sind COM-Komponenten, die Manifeste, die die DLLs integriert haben.

### <a name="to-build-manifests-into-com-components"></a>Erstellen von Manifesten in COM-Komponenten

1. Öffnen Sie die Eigenschaftenseiten des Projekts für die COM-Komponente.

1. Erweitern Sie die **Konfigurationseigenschaften** Knoten, und erweitern Sie dann die **Manifesttool** Knoten.

1. Wählen Sie die **ein- und Ausgabe** Eigenschaftenseite, und legen anschließend die **Manifest einbetten** -Eigenschaft **Ja**.

1. Klicken Sie auf **OK**.

1. Erstellen Sie die Projektmappe.

## <a name="see-also"></a>Siehe auch

[Isolierte Anwendungen](/windows/desktop/SbsCs/isolated-applications)<br/>
[Zu Seite-an-Seite-Assemblys](/windows/desktop/SbsCs/about-side-by-side-assemblies-)<br/>
[Vorgehensweise: Erstellen von isolierten Anwendungen zur Verwendung von COM-Komponenten](../build/how-to-build-isolated-applications-to-consume-com-components.md)
