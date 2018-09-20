---
title: Dialogleisten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, control bars
- CDialogBar class [MFC], dialog bars
- control bars [MFC], dialog bars
- dialog bars
- dialog bars [MFC], about dialog bars
ms.assetid: 485c8055-6bb0-4051-8417-dd2971499321
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed0e773dda8a1a31a028a0b6c5e349b2e3655982
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401497"
---
# <a name="dialog-bars"></a>Dialogleisten

Eine Dialogleiste ist eine Symbolleiste, eine Art von [Steuerleiste](../mfc/control-bars.md) , jede Art von Steuerelement enthalten kann. Da sie die Merkmale eines nicht modalen Dialogfelds, hat eine [CDialogBar](../mfc/reference/cdialogbar-class.md) Objekt eine leistungsfähigere Symbolleiste bereitgestellt.

Es gibt einige wichtige Unterschiede zwischen einer Symbolleiste und einen `CDialogBar` Objekt. Ein `CDialogBar` -Objekt wird erstellt, aus einer Dialogfeldvorlagen-Ressource, die Sie mit den Visual C++-Dialog-Editor erstellen und einem beliebigen Windows-Steuerelement enthalten kann. Der Benutzer kann vom Steuerelement steuern Registerkarte. Und Sie können angeben, dass ein Ausrichtungsart der Anpassung an die Dialogleiste mit einem beliebigen Teil der übergeordneten Rahmenfensters oder sogar um ihn beizubehalten, wenn das übergeordnete Element geändert wird. Die folgende Abbildung zeigt eine Dialogleiste mit einer Vielzahl von Steuerelementen.

![VC-Dialogleiste](../mfc/media/vc378t1.gif "vc378t1") einer Dialogleiste

In anderer Hinsicht, arbeiten mit einem `CDialogBar` Objekt ist, wie das Arbeiten mit einem nicht modalen Dialogfeld. Verwenden des Dialog-Editors zum Entwerfen und Erstellen der Dialogfeldressource an.

Die Vorteile von Dialogleisten ist, dass sie Steuerelemente, die keine Schaltflächen enthalten können.

Während der normalen aus Ihren eigenen Klassen abgeleitet ist `CDialog`, werden nicht in der Regel eine eigenen Klasse für eine Dialogleiste abgeleitet. Dialogleisten sind Erweiterungen für ein Hauptfenster und alle Dialogleiste Steuerelemente-benachrichtigungsmeldungen, z. B. **BN_CLICKED** oder **EN_CHANGE-Ereignis**, an das übergeordnete Element des Dialogfelds Balken-, das Hauptfenster gesendet werden.

## <a name="see-also"></a>Siehe auch

[Elemente der Benutzeroberfläche](../mfc/user-interface-elements-mfc.md)<br/>
[Beispiel](../visual-cpp-samples.md)

