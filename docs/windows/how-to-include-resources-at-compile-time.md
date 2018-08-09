---
title: 'Vorgehensweise: Einfügen von Ressourcen zur Kompilierungszeit | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vs.resvw.resource.including
- vc.resvw.resource.including
dev_langs:
- C++
helpviewer_keywords:
- compiling source code, including resources
- comments [C++], compiled files
- resources [Visual Studio], including at compile time
- projects [C++], including resources
- '#include directive'
- include directive (#include)
ms.assetid: 357e93c2-0a29-42f9-806f-882f688b8924
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 28374482abd5d2e039c92adbd34f261bdc259b9d
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018915"
---
# <a name="how-to-include-resources-at-compile-time"></a>Gewusst wie: Einfügen von Ressourcen zur Kompilierungszeit
Es ist für gewöhnlich einfach und intuitiv mit der Standardanordnung sämtlicher Ressourcen in einer Ressourcenskriptdatei (.rc) zu arbeiten. Aber Sie können Ressourcen hinzufügen in anderen Dateien zu Ihrem aktuellen Projekt zum Zeitpunkt der Kompilierung durch Auflisten der in der **Kompilierzeitdirektiven** im Feld der [Ressourcenincludes (Dialogfeld)](../windows/resource-includes-dialog-box.md).  
  
 Es gibt verschiedene Gründe für das Platzieren von Ressourcen in einer Datei, die von der RC-Hauptdatei abweicht:  
  
-   Zum Hinzufügen von Kommentaren zu Ressourcenanweisungen, die beim Speichern der RC-Datei nicht gelöscht werden.  
  
     Die Ressourcen-Editoren nicht direkt RC gelesen oder `resource.h` Dateien. Der Ressourcencompiler kompiliert sie in .aps-Dateien, die von den Ressourcen-Editoren genutzt werden. Diese Datei ist ein Kompilierungsschritt und speichert nur symbolische Daten. Wie bei einer normalen Kompilierung werden Informationen, die nicht symbolisch sind (z. B. Kommentare) während der Kompilierung verworfen. Sobald die .aps-Datei mit der RC-Datei nicht mehr synchron, die RC-Datei erneut generiert wird (Wenn Sie speichern, überschreibt der Ressourcen-Editor z. B. die RC-Datei und die `resource.h` Datei). Alle Änderungen an den Ressourcen selbst bleiben in der .rc-Datei, aber Kommentare gehen immer verloren, sobald die .rc-Datei überschrieben wird.  
  
-   Zum Einbeziehen von bereits entwickelten und getesteten Ressourcen, die nicht weiter geändert werden müssen. (Einbezogene Dateien ohne RC-Erweiterung können durch die Ressourcen-Editoren nicht bearbeitet werden.)  
  
-   Zum Einbeziehen von Ressourcen, die durch mehrere unterschiedliche Projekte verwendet werden oder die Bestandteil eines Quellcode-Versionssteuerungssystems sind und daher an einem zentralen Speicherort vorhanden sein müssen, wo sich die Änderungen auf alle Projekte auswirken.  
  
-   Zum Einbeziehen von Ressourcen (beispielsweise RCDATA-Ressourcen), die ein benutzerdefiniertes Format aufweisen. RCDATA-Ressourcen weisen möglicherweise spezielle Anforderungen auf. Beispielsweise können Sie einen Ausdruck für das Feld „nameID“ nicht als Wert verwenden. Weitere Informationen finden Sie in der Dokumentation zu [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
 Wenn Sie über Abschnitte in Ihren vorhandenen RC-Dateien, die eine der folgenden Bedingungen erfüllen verfügen, sollten Sie in den Abschnitten platzieren, in einem oder mehr getrennten RC-Datei, und beziehen Sie diese in Ihrem Projekt mithilfe der [Dialogfeld Ressourcenincludes](../windows/resource-includes-dialog-box.md). Die *Projectname*RC2-Datei erstellt, die im Unterverzeichnis \res eines neuen Projekts für diesen Zweck verwendet wird.  
  
### <a name="to-include-resources-in-your-project-at-compile-time"></a>So beziehen Sie Ressourcen In Ihr Projekt zum Zeitpunkt der Kompilierung ein  
  
1.  Platzieren Sie die Ressourcen in einer Ressourcenskriptdatei mit einem eindeutigen Dateinamen. Verwenden Sie keine *Projectname*RC, da es sich um die für die Haupt-Ressourcenskriptdatei verwendeten Dateinamen handelt.  
  
2.  Mit der rechten Maustaste in der RC-Datei (in [Ressourcenansicht](../windows/resource-view-window.md)), und wählen Sie **Ressourcenincludes** aus dem Kontextmenü.  
  
3.  In der **Kompilierzeitdirektiven** hinzu, und die [#include](../preprocessor/hash-include-directive-c-cpp.md) Compilerdirektive, um die neue Ressourcendatei in der Hauptressourcendatei in der Entwicklungsumgebung enthalten.  
  
     Die auf diese Weise in die Dateien einbezogenen Ressourcen werden zum Bestandteil Ihrer ausführbaren Datei zum Zeitpunkt der Kompilierung. Sie stehen nicht direkt für die Bearbeitung oder Änderung zur Verfügung, wenn Sie die RC-Hauptdatei Ihres Projekts bearbeiten. Sie müssen einbezogene RC-Dateien einzeln öffnen. Einbezogene Dateien ohne RC-Erweiterung können durch die Ressourcen-Editoren nicht bearbeitet werden.  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Ressourcendateien](../windows/resource-files-visual-studio.md)   
 [Ressourcen-Editor](../windows/resource-editors.md)