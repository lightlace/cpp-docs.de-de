---
title: Einschließlich gemeinsam genutzter (schreibgeschützter) oder berechneter Symbole | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.shared.calculated
dev_langs:
- C++
helpviewer_keywords:
- symbols [C++], read-only
- symbols [C++], shared
- symbols [C++], calculated
- read-only symbols
- symbol directives
- calculated symbols
- shared symbols
ms.assetid: 32b77faf-a066-4371-a072-9a5b84c0766d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8a2bb3a95f2b9e5506ee761906a7df213f97b927
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50061793"
---
# <a name="including-shared-read-only-or-calculated-symbols"></a>Einfügen gemeinsam genutzter (schreibgeschützter) oder berechneter Symbole

Wenn die Entwicklungsumgebung erstmals eine durch eine andere Anwendung erstellte Ressourcendatei liest, markiert sie alle einbezogenen Headerdateien als schreibgeschützt. Anschließend können Sie die [Dialogfeld Ressourcenincludes](../windows/resource-includes-dialog-box.md) um zusätzliche schreibgeschützte Symbolheaderdateien hinzuzufügen.

Ein Grund, weshalb Sie möglicherweise schreibgeschützte Symboldefinitionen verwenden möchten, ist der Plan, Symboldateien unter verschiedenen Projekten freizugeben.

Sie können zudem einbezogene Symboldateien verwenden, wenn Sie über vorhandene Ressourcen mit Symboldefinitionen verfügen, die anstelle von einfachen Ganzzahlen Ausdrücke zum Definieren des Symbolwerts verwenden. Zum Beispiel:

```cpp
#define   IDC_CONTROL1 2100
#define   IDC_CONTROL2 (IDC_CONTROL1+1)
```

Die Umgebung interpretiert diese berechneten Symbole ordnungsgemäß, sofern Folgendes gegeben ist:

- Die berechneten Symbole sind in einer schreibgeschützten Symboldatei platziert.

- Ihre Ressourcendatei enthält Ressourcen, zu denen diese berechneten Symbole bereits zugewiesen sind.

- Es wird ein numerischer Ausdruck erwartet.

> [!NOTE]
> Wenn eine Zeichenfolge oder ein numerischer Ausdruck erwartet wird, wird der Ausdruck nicht ausgewertet.

### <a name="to-include-shared-read-only-symbols-in-your-resource-file"></a>So beziehen Sie freigegebene (schreibgeschützte) Symbole in Ihrer Ressourcendatei ein

1. In [Ressourcenansicht](../windows/resource-view-window.md)mit der rechten Maustaste auf die RC-Datei, und wählen Sie [Ressourcenincludes](../windows/resource-includes-dialog-box.md) aus dem Kontextmenü.

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. In der **Anweisungen für schreibgeschützte Symbole** können Sie über die `#include` Compilerdirektive, um die Datei angeben, werden die schreibgeschützten Symbole beibehalten werden soll.

   Rufen Sie die Datei nicht `Resource.h`, da dies der Dateiname, der normalerweise durch die Hauptsymbol-Headerdatei ist.

   > [!NOTE]
   > **Wichtige** Eingabe im Feld Direktiven für schreibgeschützte Symbole in der Ressourcendatei enthalten ist, genau, wie Sie es eingeben. Stellen Sie sicher, dass die Eingabe weder Schreib- noch Syntaxfehler aufweist.

   Verwenden der **Anweisungen für schreibgeschützte Symbole** Kontrollkästchen, um Dateien mit Symboldefinitionen nur einzubeziehen. Beziehen Sie keine Ressourcendefinitionen ein. Ansonsten werden doppelte Ressourcendefinitionen erstellt, wenn die Datei gespeichert wird.

3. Platzieren Sie die Symbole in der von Ihnen angegebenen Datei.

   Die auf diese Weise in die Dateien einbezogenen Symbole werden ausgewertet, sobald Sie Ihre Ressourcendatei öffnen. Sie werden jedoch nicht auf dem Datenträger ersetzt, wenn Sie Ihre Datei speichern.

4. Klicken Sie auf **OK**.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Beschränkungen bei Symbolnamen](../windows/symbol-name-restrictions.md)<br/>
[Beschränkungen bei Symbolwerten](../windows/symbol-value-restrictions.md)<br/>
[Vordefinierte Symbol-IDs](../windows/predefined-symbol-ids.md)<br/>
[Symbole: Ressourcenbezeichner](../windows/symbols-resource-identifiers.md)