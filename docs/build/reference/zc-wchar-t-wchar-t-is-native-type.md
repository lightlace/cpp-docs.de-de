---
title: "/Zc:wchar_t (wchar_t ist der systemeigene Typ)"
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
  - "VC.Project.VCCLWCECompilerTool.TreatWChar_tAsBuiltInType"
  - "VC.Project.VCCLCompilerTool.TreatWChar_tAsBuiltInType"
  - "/Zc:wchar_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc (Compileroptionen) [C++]"
  - "Übereinstimmung (Compileroptionen)"
  - "wchar_t-Typ"
  - "Zc (Compileroptionen) [C++]"
  - "-Zc (Compileroptionen) [C++]"
ms.assetid: b0de5a84-da72-4e5a-9a4e-541099f939e0
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:wchar_t (wchar_t ist der systemeigene Typ)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Analysieren Sie `wchar_t` als integrierten Typ entsprechend dem C\+\+\-Standard.  Standardmäßig ist **\/Zc:wchar\_t** aktiviert.  
  
## Syntax  
  
```  
/Zc:wchar_t[-]  
```  
  
## Hinweise  
 Wenn **\/Zc:wchar\_t** aktiviert ist, erfolgt eine Zuordnung zwischen `wchar_t` und dem Microsoft\-spezifischen systemeigenen Typ `__wchar_t`.  Wenn **\/Zc:wchar\_t\-** \(mit einem Minuszeichen\) angegeben wird, erfolgt eine Zuordnung zwischen `wchar_t` und einer `typedef` für `unsigned short`.  \(In Visual C\+\+ 6.0 und früher wurde `wchar_t` nicht als integrierter Typ implementiert, sondern in wchar.h als `typedef` für `unsigned short` deklariert.\) Es wird davon abgeraten, **\/Zc:wchar\_t\-** zu verwenden, da gemäß C\+\+\-Standard `wchar_t` ein integrierter Typ sein muss.  Die Verwendung der `typedef`\-Version kann Portabilitätsprobleme verursachen.  Wenn Sie ein Upgrade von früheren Visual C\+\+\-Versionen durchführen und der Compilerfehler [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) auftritt, da der Code versucht, `wchar_t` implizit in `unsigned short` zu konvertieren, empfiehlt es sich, den Fehler durch eine Codeänderung zu beheben anstatt durch die Einstellung **\/Zc:wchar\_t\-**.  
  
 Microsoft implementiert `wchar_t` als 2\-Byte\-Wert ohne Vorzeichen.  Weitere Informationen zu `wchar_t` finden Sie unter [Datentypbereiche](../../cpp/data-type-ranges.md) und [Grundlegende Typen](../../cpp/fundamental-types-cpp.md).  
  
 Wenn Sie neuen Code schreiben, der mit älterem Code zusammenwirken muss, und Letzterer noch die `typedef`\-Version von `wchar_t` verwendet, können Sie Überladungen für die Varianten `unsigned short` und `__wchar_t` von `wchar_t` bereitstellen. So kann der neue Code gleichermaßen mit Code verknüpft werden, der mit oder ohne **\/Zc:wchar\_t** kompiliert wurde.  Gleichzeitig entfällt die Notwendigkeit, zwei verschiedene Builds der Bibliothek bereitzustellen \(eines mit aktiviertem **\/Zc:wchar\_t** und eines ohne\).  Allerdings wird in beiden Fällen empfohlen, den älteren und den neuen Code mit demselben Compiler zu erstellen.  Kombinieren Sie niemals die Binärdateien, die mit unterschiedlichen Compilern erstellt wurden.  
  
 Wenn **\/Zc:wchar\_t** angegeben ist, werden die Symbole **\_WCHAR\_T\_DEFINED** und **\_NATIVE\_WCHAR\_T\_DEFINED** definiert.  Weitere Informationen finden Sie unter [Vordefinierte Makros](../../preprocessor/predefined-macros.md).  
  
 Wenn der Code aufgrund der standardmäßigen Aktivierung von **\/Zc:wchar\_t** die globalen COM\-Funktionen des Compilers verwendet, empfiehlt es sich, explizite Verweise auf comsupp.lib – vom [Kommentarpragma](../../preprocessor/comment-c-cpp.md) oder von der Befehlszeile aus – in Verweise auf comsuppw.lib oder zu comsuppwd.lib zu ändern.  \(Wenn Sie mit **\/Zc:wchar\_t\-** kompilieren müssen, verwenden Sie comsupp.lib.\) Wenn Sie die comdef.h\-Headerdatei einschließen, wird die richtige Bibliothek für Sie angegeben.  Weitere Informationen zur COM\-Unterstützung des Compilers finden Sie unter [COM\-Unterstützung des Compilers](../../cpp/compiler-com-support.md).  
  
 Der Typ `wchar_t` wird nicht unterstützt, wenn Sie C\-Code kompilieren.  Weitere Informationen über Konformitätsprobleme mit Visual C\+\+ finden Sie unter [Nicht dem Standard entsprechendes Verhalten](../../cpp/nonstandard-behavior.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie im linken Bereich die Struktur **Konfigurationseigenschaften**, **C\/C\+\+** und wählen Sie dann **Sprache** aus.  
  
3.  Ändern Sie die Eigenschaft **WChar\_t als integrierten Typ behandeln**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.TreatWChar_tAsBuiltInType*>.  
  
## Siehe auch  
 [\/Zc \(Übereinstimmung\)](../../build/reference/zc-conformance.md)