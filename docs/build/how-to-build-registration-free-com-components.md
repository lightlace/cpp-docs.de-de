---
title: 'Vorgehensweise: Erstellen von registrierungsfreie COM-Komponenten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e0a9e1769ff0ba9a0589f9d59c3d1f1ed2fc5bcb
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699854"
---
# <a name="how-to-build-registration-free-com-components"></a>Gewusst wie: Erstellen von COM-Komponenten ohne Registrierung

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