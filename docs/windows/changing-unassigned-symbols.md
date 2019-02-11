---
title: Ändern oder Löschen nicht zugewiesener Symbole
ms.date: 11/04/2016
f1_keywords:
- vc.editors.symbol.changing.unassigned
helpviewer_keywords:
- symbols [C++], unassigned
- Change Symbol dialog box [C++]
- unassigned symbols
- symbols [C++], deleting
ms.assetid: b6abee4a-3c24-4697-a166-fe6a86cad35f
ms.openlocfilehash: 47cc3d7a387092afe77fdbcf4bbdb6d085eeda25
ms.sourcegitcommit: 966e4466f10c93fc12faf33d28e03b39489423fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2019
ms.locfileid: "55987013"
---
# <a name="changing-or-deleting-unassigned-symbols"></a>Ändern oder Löschen nicht zugewiesener Symbole

Während Sie sich in der [Ressourcensymbole (Dialogfeld)](../windows/resource-symbols-dialog-box.md), können Sie bearbeiten oder löschen Sie vorhandene Symbole, die bereits auf eine Ressource oder das Objekt zugewiesen wird.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*.

## <a name="to-change-an-unassigned-symbol"></a>So ändern Sie ein nicht zugewiesenes Symbol

1. In der **Namen** Feld, das nicht zugewiesene Symbol auswählen, und wählen **Änderung**.

1. Bearbeiten des Symbols oder -Wert in den angezeigten Feldern der **Symbol ändern** Dialogfeld.

   > [!NOTE]
   > So ändern Sie ein Symbol, *ist* , eine Ressource oder einem Objekt zugewiesen wird, müssen Sie den Ressourcen-Editor verwenden oder **Eigenschaften** Fenster. Weitere Informationen finden Sie unter [Ändern eines Symbols oder Symbolnamens](../windows/changing-a-symbol-or-symbol-name-id.md).

## <a name="to-delete-an-unassigned-unused-symbol"></a>So löschen Sie ein nicht zugewiesenes (nicht verwendetes) Symbol

In der [Dialogfeld Ressourcensymbole](../windows/resource-symbols-dialog-box.md), wählen Sie das Symbol, das Sie verwenden möchten, löschen, und wählen Sie **löschen**.

   > [!NOTE]
   > Stellen Sie vor dem Löschen eines nicht verwendeten Symbols in einer Ressourcendatei sicher, dass es nicht an anderer Stelle im Programm oder durch die Ressourcendateien zum Zeitpunkt der Kompilierung verwendet wird.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Anzeigen von Ressourcensymbolen](../windows/viewing-resource-symbols.md)<br/>
[Beschränkungen bei Symbolnamen](../windows/symbol-name-restrictions.md)<br/>
[Beschränkungen bei Symbolwerten](../windows/symbol-value-restrictions.md)<br/>
[Vordefinierte Symbol-IDs](../windows/predefined-symbol-ids.md)