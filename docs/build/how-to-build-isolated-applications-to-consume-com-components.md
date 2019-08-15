---
title: 'Vorgehensweise: Erstellen isolierter Anwendungen für die Nutzung von COM-Komponenten'
ms.date: 11/04/2016
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 04587547-1174-44ab-bd99-1292358fba20
ms.openlocfilehash: 8ae3c51502267f202cbb85ea7be2a81dc3310410
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493236"
---
# <a name="how-to-build-isolated-applications-to-consume-com-components"></a>Vorgehensweise: Erstellen isolierter Anwendungen für die Nutzung von COM-Komponenten

Isolierte Anwendungen sind Anwendungen, deren Manifeste in das Programm integriert sind. Sie können isolierte Anwendungen erstellen, um COM-Komponenten zu verwenden.

### <a name="to-add-com-references-to-manifests-of-isolated-applications"></a>So fügen Sie com-Verweise zu Manifesten von isolierten Anwendungen hinzu

1. Öffnen Sie die Projekteigenschaften Seiten für die isolierte Anwendung.

1. Erweitern Sie den Knoten **Konfigurations Eigenschaften** , und erweitern Sie dann den Knoten **Manifest-Tool** .

1. Wählen Sie die Eigenschaften Seite **isolierte com** aus, und legen Sie dann die Eigenschaft **Komponenten** Dateiname auf den Namen der COM-Komponente fest, die von der isolierten Anwendung verwendet werden soll.

1. Klicken Sie auf **OK**.

### <a name="to-build-manifests-into-isolated-applications"></a>So erstellen Sie Manifeste in isolierten Anwendungen

1. Öffnen Sie die Projekteigenschaften Seiten für die isolierte Anwendung.

1. Erweitern Sie den Knoten **Konfigurations Eigenschaften** , und erweitern Sie dann den Knoten **Manifest-Tool** .

1. Wählen Sie die Eigenschaften Seite **Eingabe und Ausgabe** aus, und legen Sie dann die Eigenschaft das **Einbettungs Manifest** auf **Ja**fest.

1. Klicken Sie auf **OK**.

1. Erstellen Sie die Projektmappe.

## <a name="see-also"></a>Siehe auch

[Isolierte Anwendungen](/windows/win32/SbsCs/isolated-applications)<br/>
[Informationen zu parallelen Assemblys](/windows/win32/SbsCs/about-side-by-side-assemblies-)
