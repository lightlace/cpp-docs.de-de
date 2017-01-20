---
title: "Dialogfeld &quot;Ressource hinzuf&#252;gen&quot;"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.editors.insertresource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ressourcen [Visual Studio], hinzufügen"
  - "Ressource hinzufügen (Dialogfeld)"
ms.assetid: e9fb6967-738f-47e8-ab58-728cf35b3af0
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Dialogfeld &quot;Ressource hinzuf&#252;gen&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie dieses Dialogfeld zum Hinzufügen von Ressourcen zu einem C\+\+\-Windows\-Desktopanwendungs\-Projekt.  
  
> [!NOTE]
>  Diese Informationen gelten nicht für Ressourcen in Windows Store\-Apps. Weitere Informationen hierzu finden Sie unter [Definieren von App\-Ressourcen](assetId:///476ea844-632c-4467-9ce3-966be1350dd4).  
  
 **Ressourcentyp**  
 Gibt die Art der zu erstellenden Ressource an.  
  
 Der Cursor und die Kategorien der Dialogfeldressourcen können zum Anzeigen zusätzlicher Ressourcen erweitert werden. Diese Ressourcen befinden sich im Verzeichnis „...\\Microsoft Visual Studio `Version`\\VC\\VCResourceTemplates\\\<LCID\>\\mfc.rct“. Wenn Sie RCT\-Dateien hinzufügen, müssen sie in diesem Verzeichnis abgelegt werden, oder Sie müssen einen [Includepfad](../windows/how-to-specify-include-directories-for-resources.md) für die Dateien angeben. Die Ressourcen in diesen Dateien werden dann auf der zweiten Ebene der entsprechenden Kategorie angezeigt. Die Anzahl von RCT\-Dateien, die hinzugefügt werden können, ist nicht beschränkt.  
  
 Die auf der obersten Ebene der Strukturansicht angezeigten Ressourcen sind die von Visual Studio bereitgestellten Standardressourcen.  
  
 **Neu**  
 Erstellt eine Ressource auf der Grundlage des Typs, den Sie im Feld **Ressourcentyp** ausgewählt haben. Die Ressource wird im geeigneten Editor geöffnet. Beim Erstellen einer Dialogfeldressource öffnen sie sich im [Dialog\-Editor](../mfc/dialog-editor.md).  
  
 **Importieren**  
 Öffnet das Dialogfeld **Importieren**, in dem Sie zu einer beliebigen Ressource navigieren können, die in das aktuelle Projekt importiert werden soll. Sie können eine Bitmap, ein Symbol, einen Cursor, eine HTML\-Ressourcendatei, eine Sound\-Ressourcendatei \(.WAV\) oder eine benutzerdefinierte Ressourcendatei importieren.  
  
 **Benutzerdefiniert**  
 Öffnet das [Dialogfeld "Neue benutzerdefinierte Ressource"](../windows/new-custom-resource-dialog-box.md), in dem Sie eine benutzerdefinierte Ressource erstellen können. Benutzerdefinierte Ressourcen können nur im Binär\-Editor bearbeitet werden.  
  
## Anforderungen  
 Keine  
  
## Siehe auch  
 [How to: Create a Resource](../windows/how-to-create-a-resource.md)