---
title: Anzeigen von Ressourcensymbolen (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.symbol.managing
- vc.editors.resourcesymbols
helpviewer_keywords:
- resources [C++], viewing
- resource symbols
- symbols [C++], viewing
- New Symbol dialog box [C++]
- Resource Symbols dialog box [C++]
- Change Symbol dialog box [C++]
ms.assetid: 4bcc06d9-7d36-486a-8a37-71da0541643c
ms.openlocfilehash: e61269261fc9172288f1edf58419009178c755d9
ms.sourcegitcommit: 63c072f5e941989636f5a2b13800b68bb7129931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "55763972"
---
# <a name="viewing-resource-symbols"></a>Anzeigen von Ressourcensymbolen

Die **Ressourcensymbole** C++-Dialogfeld können Sie neue Ressourcensymbole hinzufügen, ändern die Symbole, die angezeigt werden, oder fahren Sie mit der Position im Quellcode, in denen ein Symbol verwendet wird.

Das Dialogfeld enthält die folgenden Eigenschaften:

|Eigenschaft|Beschreibung|
|---|---|
|**Name**|Zeigt den Namen des Symbols an. Weitere Informationen finden Sie unter [Beschränkungen bei Symbolnamen](../windows/symbol-name-restrictions.md).|
|**Wert**|Zeigt den numerischen Wert des Symbols an. Weitere Informationen finden Sie unter [Beschränkungen für Symbolwerte](../windows/symbol-value-restrictions.md).|
|**In Verwendung**|Bei Auswahl dieser Option wird angegeben, dass das Symbol von einer oder mehreren Ressourcen verwendet wird. Die Ressourcen sind im Feld „Verwendet von aufgeführt“.|
|**Schreibgeschützte Symbole anzeigen**|Bei Auswahl dieser Option werden schreibgeschützte Ressourcen angezeigt. In der Standardeinstellung die **Ressourcensymbol** im Dialogfeld werden nur die änderbaren Ressourcen in Ihrer Ressourcenskriptdatei angezeigt, aber diese Option ausgewählt ist, werden änderbare Ressourcen fett und schreibgeschützte Ressourcen werden im nur-Text angezeigt.|
|**Verwendet von**|Zeigt die Ressource bzw. Ressourcen an, in der/denen das in der Symbolliste markierte Symbol verwendet wird. Um in den Editor für eine bestimmte Ressource verschieben möchten, wählen Sie die Ressource in der **verwendet von** ein, und klicken Sie auf **Verwendung anzeigen**. Weitere Informationen finden Sie unter [Öffnen des Ressourcen-Editors für ein bestimmtes Symbol](../windows/opening-the-resource-editor-for-a-given-symbol.md).|
|**Neu**|Öffnet die **neues Symbol** Dialogfeld, das Ihnen ermöglicht, definieren den Namen und, falls erforderlich, einen Wert für einen neuen symbolischen Ressourcenbezeichner. Weitere Informationen finden Sie unter [Erstellen neuer Symbole](../windows/creating-new-symbols.md).|
|**Änderung**|Öffnet die **Symbol ändern** im Dialogfeld, in dem Sie den Namen oder Wert eines Symbols ändern kann. Wenn das Symbol für ein Steuerelement oder eine Ressource in Gebrauch ist, kann das Symbol nur im entsprechenden Ressourcen-Editor geändert werden. Weitere Informationen finden Sie unter [ändern nicht zugewiesener Symbole](../windows/changing-unassigned-symbols.md).|
|**Verwendung anzeigen**|Öffnet die Ressource, die das Symbol enthält, im entsprechenden Ressourcen-Editor. Weitere Informationen finden Sie unter [Öffnen des Ressourcen-Editors für ein bestimmtes Symbol](../windows/opening-the-resource-editor-for-a-given-symbol.md).|

## <a name="to-view-resource-symbols"></a>So zeigen Sie Ressourcensymbole an

1. In [Ressourcenansicht](../windows/resource-view-window.md), mit der rechten Maustaste in der RC-Datei.

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

1. Wählen Sie **Ressourcensymbole** aus dem Kontextmenü zum Anzeigen einer Ressourcensymboltabelle im der **Ressourcensymbole** Dialogfeld.

   > [!NOTE]
   > Vordefinierte Symbole sehen Sie die **schreibgeschützte Symbole anzeigen** Kontrollkästchen.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Symbole: Ressourcenbezeichner](../windows/symbols-resource-identifiers.md)