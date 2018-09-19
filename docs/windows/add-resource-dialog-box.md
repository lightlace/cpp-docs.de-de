---
title: Hinzufügen (Dialogfeld) (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.insertresource
dev_langs:
- C++
helpviewer_keywords:
- resources [C++], adding
- Add Resource dialog box [C++]
ms.assetid: e9fb6967-738f-47e8-ab58-728cf35b3af0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f44a0be0fc7614ab9dd09e814e7e444ed90e8a4a
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44317666"
---
# <a name="add-resource-dialog-box"></a>Ressource hinzufügen (Dialogfeld)

Verwenden Sie dieses Dialogfeld zum Hinzufügen von Ressourcen zu einem C++-Windows-Desktopanwendungs-Projekt.

> [!NOTE]
> Diese Informationen gelten nicht für Ressourcen in den apps der universellen Windows-Plattform. Weitere Informationen finden Sie unter [App-Ressourcen und das Ressourcenverwaltungssystem](/windows/uwp/app-resources/).

### <a name="resource-type"></a>Ressourcentyp

Gibt die Art der zu erstellenden Ressource an.

Der Cursor und die Kategorien der Dialogfeldressourcen können zum Anzeigen zusätzlicher Ressourcen erweitert werden. Diese Ressourcen befinden sich im Visual Studio-...\Microsoft `version`\VC\VCResourceTemplates\\< LCID\>\mfc.rct. Wenn Sie RCT-Dateien hinzufügen, Sie sie in diesem Verzeichnis ablegen müssen oder Sie angeben müssen, ein [Includepfad](../windows/how-to-specify-include-directories-for-resources.md) für sie. Die Ressourcen in diesen Dateien werden dann auf der zweiten Ebene der entsprechenden Kategorie angezeigt. Die Anzahl von RCT-Dateien, die hinzugefügt werden können, ist nicht beschränkt.

Die auf der obersten Ebene der Strukturansicht angezeigten Ressourcen sind die von Visual Studio bereitgestellten Standardressourcen.

### <a name="new"></a>Neu

Erstellt eine Ressource anhand des Typs, die Sie, in ausgewählt haben der **Ressourcentyp** Feld. Die Ressource wird im geeigneten Editor geöffnet. Beispielsweise wenn Sie eine Ressource erstellen, es öffnet der [Dialog-Editor](../windows/dialog-editor.md).

### <a name="import"></a>Importieren

Öffnet die **importieren** Dialogfeld, in dem gelangen Sie zu einer Ressource Sie, möchten in Ihrem aktuellen Projekt zu importieren. Sie können eine Bitmap, ein Symbol, einen Cursor, eine HTML-Ressourcendatei, eine Sound-Ressourcendatei (.WAV) oder eine benutzerdefinierte Ressourcendatei importieren.

### <a name="custom"></a>Benutzerdefiniert

Öffnet die [Dialogfeld neue benutzerdefinierte Ressource](../windows/new-custom-resource-dialog-box.md) in dem Sie eine benutzerdefinierte Ressource erstellen können. Benutzerdefinierte Ressourcen können nur im Binär-Editor bearbeitet werden.

## <a name="requirements"></a>Anforderungen

Keiner

## <a name="see-also"></a>Siehe auch

[Vorgehensweise: Erstellen einer Ressource](../windows/how-to-create-a-resource.md)