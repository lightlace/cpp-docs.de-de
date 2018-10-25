---
title: Hinzufügen von Verbindungspunkten zu einem Objekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], adding to ATL objects
- Implement Connection Point ATL wizard
ms.assetid: 843531be-4a36-4db0-9d54-e029b1a72a8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 685f1b7d24e781dbee6d67b325b059f09ca9bf4c
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50054214"
---
# <a name="adding-connection-points-to-an-object"></a>Hinzufügen von Verbindungspunkten zu einem Objekt

Die [ATL-Lernprogramm](../atl/active-template-library-atl-tutorial.md) wird veranschaulicht, wie Sie ein Steuerelement mit Unterstützung von Verbindungspunkten erstellen, wie Sie Ereignisse hinzufügen und wie Sie den Verbindungspunkt implementieren. ATL implementiert Verbindungspunkte, die mit der [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) Klasse.

Um einen Verbindungspunkt implementieren zu können, haben Sie zwei Möglichkeiten:

- Implementieren Sie eigene ausgehenden Ereignisquelle, durch das Hinzufügen von eines Verbindungspunkts an das Steuerelement oder das Objekt.

- Wiederverwenden von einem Verbindungspunkt-Schnittstelle in einer anderen Typbibliothek definiert.

In beiden Fällen verwendet der Assistent zum Implementieren von Verbindungspunkten eine Typbibliothek, um seine Arbeit zu erledigen.

### <a name="to-add-a-connection-point-to-a-control-or-object"></a>Um ein Steuerelement oder das Objekt einen Verbindungspunkt hinzufügen

1. Definieren Sie eine Disp-Schnittstelle, in den bibliotheksblock der IDL-Datei. Wenn Sie Unterstützung von Verbindungspunkten aktiviert, wenn Sie das Steuerelement mit dem ATL-Steuerelement-Assistenten erstellt, wird die Disp-Schnittstelle bereits erstellt worden sein. Wenn Sie nicht Unterstützung für Verbindungspunkte aktiviert haben, wenn Sie das Steuerelement erstellt haben, müssen Sie manuell eine Disp-Schnittstelle der IDL-Datei hinzufügen. Folgendes ist ein Beispiel für eine Disp-Schnittstelle. Ausgangsschnittstellen sind nicht erforderlich, um die Dispatch-Schnittstellen werden jedoch viele Skriptsprachen wie VBScript und JScript erforderlich, damit dieses Beispiel zwei Disp-Schnittstellen verwendet:

   [!code-cpp[NVC_ATL_Windowing#81](../atl/codesnippet/cpp/adding-connection-points-to-an-object_1.idl)]

   Verwenden Sie entweder die uuidgen.exe oder guidgen.exe-Hilfsprogramm zum Generieren eines GUIDs.

2. Fügen Sie die Disp-Schnittstelle als die `[default,source]` -Schnittstelle in der Co-Klasse für das Objekt in die IDL-Datei des Projekts. In diesem Fall, wenn Sie Unterstützung von Verbindungspunkten aktiviert, wenn Sie das Steuerelement erstellt, die ATL-Steuerelement-Assistent erstellt die `[default,source`] Eintrag. Um diesen Eintrag manuell hinzuzufügen, fügen Sie die Zeile in Fettschrift angezeigt:

   [!code-cpp[NVC_ATL_Windowing#82](../atl/codesnippet/cpp/adding-connection-points-to-an-object_2.idl)]

   Finden Sie in der IDL-Datei in die [Circ](../visual-cpp-samples.md) ATL-Beispiel für ein Beispiel.

3. Mithilfe der Klassenansicht so Ereignisschnittstelle Methoden und Eigenschaften hinzu. Mit der rechten Maustaste in der Klasse in der Klassenansicht, zeigen Sie auf **hinzufügen** auf das Kontextmenü, und klicken Sie auf **Verbindungspunkt hinzufügen**.

4. In der **Quellschnittstellen** Listenfeld implementieren Verbindung zeigen Assistenten die Option **Projektschnittstellen**. Eine Schnittstelle für Ihr Steuerelement, und drücken Sie auf Wunsch **OK**, Sie werden:

   - Erstellen Sie eine Headerdatei mit einer Ereignis-Proxy-Klasse, die den Code implementiert, der die ausgehende Aufrufe für das Ereignis machen werden.

   - Fügen Sie einen Eintrag, der Connection Point-Zuordnung.

   Sie sehen auch eine Liste aller der Typbibliotheken auf Ihrem Computer. Sie sollten nur anhand einer anderen Typbibliotheken Connection Point zu definieren, wenn Sie genaue dieselbe Ausgangsschnittstelle finden Sie in einer anderen Typbibliothek implementieren möchten.

### <a name="to-reuse-a-connection-point-interface-defined-in-another-type-library"></a>Wiederverwenden von einem Verbindungspunkt-Schnittstelle definiert, in einer anderen Typbibliothek

1. In der Klassenansicht mit der Maustaste einer Klasse, implementiert eine **BEGIN_COM_MAP** -Makro, zeigen Sie auf **hinzufügen** auf das Kontextmenü, und klicken Sie auf **Verbindungspunkt hinzufügen**.

2. Klicken Sie in der Verbindung Assistent zum Implementieren, wählen Sie in der Typbibliothek einer Typbibliothek und eine Schnittstelle, und klicken Sie auf **hinzufügen**.

3. Bearbeiten der IDL-Datei entweder an:

   - Kopieren Sie die Disp-Schnittstelle aus der .idl-Datei für das Objekt, dessen Ereignisquelle verwendet wird.

   - Verwenden der **Importlib** Anweisung auf die Typbibliothek.

## <a name="see-also"></a>Siehe auch

[Verbindungspunkt](../atl/atl-connection-points.md)

