---
title: "Verwenden der CArchive-Operatoren &lt;&lt; und &gt;&gt;"
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
  - "CArchive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive-Klasse, Operatoren"
  - "CArchive-Klasse, Speichern und Laden von Objekten"
  - "Objekte [C++], Laden aus zuvor gespeicherten Werten"
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden der CArchive-Operatoren &lt;&lt; und &gt;&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CArchive` stellt \<\< und \>\>\-Operatoren für das Schreiben und Lesen von einfachen Datentypen sowie `CObject`s in und aus einer Datei.  
  
#### Um ein Objekt in einer Datei zu einem Archiv speichern  
  
1.  Das folgende Beispiel zeigt, wie ein Objekt in einer Datei zu einem Archiv speichert:  
  
     [!CODE [NVC_MFCSerialization#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSerialization#7)]  
  
#### Um ein Objekt einem Wert laden zuvor gespeichert in einer Datei  
  
1.  Im folgenden Beispiel wird gezeigt, wie ein Objekt von einem Wert geladen, der zuvor in einer Datei gespeichert wird:  
  
     [!CODE [NVC_MFCSerialization#8](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSerialization#8)]  
  
 Normalerweise speichern und laden Daten in und aus einer Datei zu einem Archiv in den Funktionen `Serialize` von `CObject` abgeleitete Klassen, die Sie mit dem **DECLARE\_SERIALIZE**\-Makro deklariert haben müssen.  Ein Verweis auf ein `CArchive`\-Objekt wird auf der `Serialize`\-Funktion übergeben.  Sie rufen die `IsLoading`\-Funktion des `CArchive`\-Objekts auf, um zu bestimmen, ob die Funktion `Serialize` aufgerufen wurde, um Daten von den Datei\- oder Daten in die Datei zu laden.  
  
 Die `Serialize`\-Funktion von serialisierbaren `CObject` abgeleitete Klasse verfügt normalerweise folgende Form:  
  
 [!CODE [NVC_MFCSerialization#9](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSerialization#9)]  
  
 Die oben aufgeführten Codevorlage ist genau identisch, die der eines Anwendungs\-Assistent für die `Serialize`\-Funktion des Dokuments erstellt \(eine Klasse abgeleitet von **CDocument\)**.  Diese Codevorlage hilft Ihnen, Code zu schreiben, der leichter, da der speichernde Code und der Ladencode immer parallel sein sollten, wie im folgenden Beispiel zu überprüfen ist:  
  
 [!CODE [NVC_MFCSerialization#10](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSerialization#10)]  
  
 Die Bibliothek definiert **\<\<** und **\>\>** für Operatoren `CArchive` als erste Operand und die folgenden Datentypen und die Klassentypen als der zweite Operand:  
  
||||  
|-|-|-|  
|`CObject*`|**GRÖSSE und CSize**|**float**|  
|**WORD**|`CString`|**PUNKT** und `CPoint`|  
|`DWORD`|**BYTE**|`RECT` und `CRect`|  
|**Double**|**LONG**|`CTime` und `CTimeSpan`|  
|`Int`|**COleCurrency**|`COleVariant`|  
|`COleDateTime`|`COleDateTimeSpan`||  
  
> [!NOTE]
>  Das Speichern und Laden von `CObject`s zu einem Archiv erfordert zusätzliche Überlegung.  Weitere Informationen finden Sie unter [CObjects zu einem Archiv Speichern und Laden](../mfc/storing-and-loading-cobjects-via-an-archive.md).  
  
 Die **CArchive \<\<** und **\>\>**\-Operatoren geben immer einen Verweis auf das `CArchive`\-Objekt zurück, das der erste Operand ist.  Dies ermöglicht es Ihnen, die Operatoren zu verketten, wie unten dargestellt:  
  
 [!CODE [NVC_MFCSerialization#11](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSerialization#11)]  
  
## Siehe auch  
 [Serialisierung: Serialisieren eines Objekts](../mfc/serialization-serializing-an-object.md)