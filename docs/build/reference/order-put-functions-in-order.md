---
title: "/ORDER (Reihenfolge von Funktionen festlegen)"
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
  - "VC.Project.VCLinkerTool.FunctionOrder"
  - "/order"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ORDER (Linkeroption)"
  - "LINK-Tool [C++], Programmoptimierung"
  - "LINK-Tool [C++], Auslagerungsdatei optimieren"
  - "ORDER (Linkeroption)"
  - "-ORDER (Linkeroption)"
  - "Paging, Optimieren"
ms.assetid: ecf5eb3e-e404-4e86-9a91-4e5ec157261a
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# /ORDER (Reihenfolge von Funktionen festlegen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ORDER:@filename  
```  
  
## Parameter  
 *filename*  
 eine Textdatei, die die Reihenfolge beim Verknüpfen der COMDAT\-Funktionen festlegt.  
  
## Hinweise  
 Die \/ORDER\-Option weist LINK an, das Programm durch Platzieren bestimmter COMDATs im Image in einer vorbestimmten Reihenfolge zu optimieren.  LINK positioniert die Funktionen in der angegebenen Reihenfolge innerhalb jedes Abschnitts im Image.  
  
 Geben Sie die Reihenfolge in *filename* an. Dies ist eine Textdatei \(Antwortdatei\), in der die COMDATs in der von Ihnen gewünschten Reihenfolge zum Verknüpfen aufgeführt sind.  Jede Zeile in *filename* enthält den Namen einer COMDAT.  Ein Objekt enthält COMDATs, wenn es mit der Option **\/Gy** kompiliert worden ist.  Bei Funktionsnamen muss die Groß\-\/Kleinschreibung beachtet werden.  
  
 **LINK** verwendet die ergänzten Formen von Bezeichnern.  Vom Compiler wird den Bezeichnern beim Erstellen der OBJ\-Datei eine Ergänzung hinzugefügt.  Verwenden Sie das Tool [DUMPBIN](../../build/reference/dumpbin-reference.md), um die ergänzte Form eines Bezeichners zu ermitteln, wenn Sie diese dem Linker angeben müssen.  Weitere Informationen über ergänzte Namen finden Sie unter [Ergänzte Namen](../../build/reference/decorated-names.md).  
  
 Wenn mehr als eine **\/ORDER**\-Spezifikation verwendet wird, tritt die zuletzt angegebene in Kraft.  
  
 Die Angabe einer Reihenfolge ermöglicht es Ihnen, das Verhalten Ihres Programms durch Feineinstellung der Auslagerung von Speicherseiten zu optimieren, indem eine Funktion mit der von ihr aufgerufenen Funktion zusammen angeordnet wird.  Sie können auch häufig aufgerufene Funktionen zusammen gruppieren.  Durch dieses Vorgehen wird die Wahrscheinlichkeit erhöht, dass eine aufgerufene Funktion sich bereits im Hauptspeicher befindet, wenn sie benötigt wird, und nicht erst vom Datenträger gelesen werden muss.  
  
 Der Linker stellt jedem ergänzten Namen in *filename* einen Unterstrich \(\_\) voran, sofern der Name nicht mit einem Fragezeichen \(?\) oder einem @\-Zeichen beginnt.  Wenn eine Objektdatei z. B. die Zeichenkette `extern "C" int func(int)` und `int main(void)` enthält, werden diese ergänzten Namen mit **DUMPBIN**[\/SYMBOLS](../../build/reference/symbols.md) aufgelistet:  
  
```  
009 00000000 SECT3  notype ()    External     | _func  
00A 00000008 SECT3  notype ()    External     | _main  
```  
  
 Der in der Anordnungsdatei angegebene Name sollte jedoch `func` und `main` enthalten.  
  
 Die Option **\/ORDER** deaktiviert das inkrementelle Verknüpfen.  
  
> [!NOTE]
>  LINK kann statische Funktionen nicht anordnen, da es sich bei statischen Funktionsnamen nicht um öffentliche Symbolnamen handelt.  Bei Eingabe von **\/ORDER** wird für jedes Symbol, das entweder statisch ist oder nicht gefunden werden kann, in die Anordnungsdatei die Linkerwarnung LNK4037 ausgegeben.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Optimierung**.  
  
4.  Ändern Sie die Eigenschaft **Funktionsanordnung**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.FunctionOrder*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)