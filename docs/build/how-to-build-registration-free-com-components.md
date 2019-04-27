---
title: 'Vorgehensweise: Erstellen Sie die Registrierung von COM-Komponenten'
ms.date: 11/04/2016
helpviewer_keywords:
- COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
ms.openlocfilehash: 783677c97835acc98751fc4a19f9405af752b71a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188937"
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

[Vorgehensweise: Erstellen von isolierten Anwendungen zur Verwendung von COM-Komponenten](how-to-build-isolated-applications-to-consume-com-components.md)
