---
title: 'Vorgehensweise: Erstellen Sie die Symbole (C++)'
ms.date: 02/14/2019
f1_keywords:
- vc.editors.symbol.creating
- vc.editors.symbol.managing
- vc.editors.resourcesymbols
- vc.editors.symbol.resource
helpviewer_keywords:
- New Symbol dialog box [C++]
- symbols [C++], creating
- resources [C++], viewing
- resource symbols
- symbols [C++], viewing
- New Symbol dialog box [C++]
- Resource Symbols dialog box [C++]
- Change Symbol dialog box [C++]
- resource symbols
- View Use button
- resource editors [C++], resource symbols
ms.assetid: 35168d31-3af6-4ecd-9362-3707d47b53f3
ms.openlocfilehash: d03246d2c701961c824b55fb0cbb781ee3f65028
ms.sourcegitcommit: 6cf0c67acce633b07ff31b56cebd5de3218fd733
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2019
ms.locfileid: "67344202"
---
# <a name="how-to-create-symbols-c"></a>Vorgehensweise: Erstellen Sie die Symbole (C++)

Wenn Sie ein neues Projekt beginnen, kann es zweckmäßig sein, Symbolnamen zuzuordnen, die Sie vor dem Erstellen der Ressourcen, die sie zugewiesen werden, müssen.

> [!NOTE]
> Wenn Ihr Projekt noch keine RC-Datei enthält, finden Sie unter [Vorgehensweise: Erstellen von Ressourcen](../windows/how-to-create-a-resource-script-file.md).

Die **Ressourcensymbole** Dialogfeld können Sie neue Ressourcensymbole hinzufügen, ändern die Symbole, die angezeigt werden, oder fahren Sie mit der Position im Quellcode, in denen ein Symbol verwendet wird.

Das Dialogfeld enthält die folgenden Eigenschaften:

|Eigenschaft|Beschreibung|
|--------------------------|------------------------------------------|
|**Name**|Zeigt den Namen des Symbols an.<br/><br/>Weitere Informationen finden Sie unter [Beschränkungen bei Symbolnamen](../windows/symbol-name-restrictions.md).|
|**Wert**|Zeigt den numerischen Wert des Symbols an.<br/><br/>Weitere Informationen finden Sie unter [Beschränkungen für Symbolwerte](../windows/symbol-value-restrictions.md).|
|**In Verwendung**|Bei Auswahl dieser Option wird angegeben, dass das Symbol von einer oder mehreren Ressourcen verwendet wird.<br/><br/>Die Ressource bzw. Ressourcen finden Sie in der **von verwendeten** Feld.|
|**Schreibgeschützte Symbole anzeigen**|Bei Auswahl dieser Option werden schreibgeschützte Ressourcen angezeigt.<br/><br/>In der Standardeinstellung die **Ressourcensymbol** im Dialogfeld werden nur die änderbaren Ressourcen in Ihrer Ressourcenskriptdatei angezeigt, aber diese Option ausgewählt ist, werden änderbare Ressourcen fett und schreibgeschützte Ressourcen werden im nur-Text angezeigt.|
|**Verwendet von**|Zeigt die Ressource bzw. Ressourcen an, in der/denen das in der Symbolliste markierte Symbol verwendet wird.<br/><br/>Um in den Editor für eine bestimmte Ressource verschieben möchten, wählen Sie die Ressource in der **ein, die** und **Verwendung anzeigen**.|
|**Neu**|Öffnet die **neues Symbol** Dialogfeld, das Ihnen ermöglicht, definieren den Namen und, falls erforderlich, einen Wert für einen neuen symbolischen Ressourcenbezeichner.|
|**Änderung**|Öffnet die **Symbol ändern** Dialogfeld, das Ihnen ermöglicht, den Namen oder Wert eines Symbols zu ändern.<br/><br/>Wenn das Symbol für ein Steuerelement oder eine Ressource in Gebrauch ist, kann das Symbol nur im entsprechenden Ressourcen-Editor geändert werden. Weitere Informationen finden Sie unter [verwalten Symbole](../windows/changing-unassigned-symbols.md).|
|**Verwendung anzeigen**|Öffnet die Ressource, die das Symbol enthält, im entsprechenden Ressourcen-Editor.|

## <a name="create-symbols"></a>Erstellen von Symbolen

### <a name="to-create-a-new-symbol"></a>Erstellen Sie ein neues symbol

1. In der **Ressourcensymbole** Dialogfeld wählen **neu**.

1. In der **Namen** geben einen Symbolnamen an.

1. Akzeptieren Sie den zugewiesenen Symbolwert, oder geben Sie einen neuen Wert in der **Wert** Feld.

1. Wählen Sie **OK** der Symbolliste das neue Symbol hinzu.

> [!NOTE]
> Wenn Sie einen bereits vorhandenen Symbolnamen eingeben, wird eine Meldung angezeigt, aus der hervorgeht, dass ein Symbol mit diesem Namen bereits definiert ist. Sie können nicht zwei oder mehr Symbole mit demselben Namen definieren, aber Sie können unterschiedliche Symbole mit demselben numerischen Wert definieren.

## <a name="to-view-resource-symbols"></a>So zeigen Sie Ressourcensymbole an

In [Ressourcenansicht](how-to-create-a-resource-script-file.md#create-resources), mit der rechten Maustaste Ihre *RC* und wählen Sie **Ressourcensymbole** anzeigen eine Ressourcensymboltabelle im der **Ressourcensymbole**Dialogfeld.

> [!NOTE]
> Vordefinierte Symbole sehen Sie die **schreibgeschützte Symbole anzeigen** Kontrollkästchen.

### <a name="to-open-the-resource-editor-for-a-given-symbol"></a>Öffnen des Ressourcen-Editors für ein bestimmtes symbol

Wenn Sie Symbole im Durchsuchen der **Ressourcensymbole**, sollten Sie weitere Informationen zur Verwendung ein bestimmtes Symbols. Die **Verwendung anzeigen** Schaltfläche bietet eine schnelle Möglichkeit zum Abrufen dieser Informationen.

1. In der **Ressourcensymbole** im Dialogfeld die **Namen** wählen ein Symbol.

1. In der **verwendet von** wählen den Ressourcentyp aus, die Sie interessieren.

1. Wählen Sie die **Verwendung anzeigen** Schaltfläche.

   Die Ressource wird im geeigneten Editor-Fenster geöffnet.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcenbezeichner (Symbole)](../windows/symbols-resource-identifiers.md)<br/>
[Vorgehensweise: Verwalten von Symbolen](../windows/changing-a-symbol-or-symbol-name-id.md)<br/>
[Vordefinierte Symbol-IDs](../windows/predefined-symbol-ids.md)<br/>