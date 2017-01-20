---
title: "/Zc:strictStrings (Zeichenfolgenliteral-Typkonvertierung deaktivieren)"
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
  - "/Zc:strictStrings"
  - "strictStrings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc (Compileroptionen) [C++]"
  - "/Zc:strictStrings"
  - "strictStrings"
  - "Zc (Compileroptionen) [C++]"
  - "-Zc (Compileroptionen) [C++]"
ms.assetid: b7eb3f3b-82c1-48a2-8e63-66bad7397b46
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:strictStrings (Zeichenfolgenliteral-Typkonvertierung deaktivieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn dies angegeben wird, benötigt der Compiler eine strenge `const`\-Qualifikationsübereinstimmung für Zeiger, die mithilfe von Zeichenfolgenliteralen initialisiert werden.  
  
## Syntax  
  
```  
/Zc:strictStrings[-]  
```  
  
## Hinweise  
 Wenn **\/Zc:strictStrings** angegeben wird, erzwingt der Compiler die standardmäßigen C\+\+ `const`\-Qualifikationen für Zeichenfolgenliterale, als Typ "Array von `const` `char`" oder "Array von `const` `wchar_t`", abhängig von der Deklaration.  Zeichenfolgenliterale sind unveränderlich. Der Versuch, den Inhalt von einem von ihnen zu ändern, führt zu einem Zugriffsverletzungsfehler in der Laufzeit.  Sie müssen einen Zeichenfolgenzeiger als `const` deklarieren, um ihn mithilfe eines Zeichenfolgenliterals zu initialisieren, oder sie müssen eine explizite `const_cast` verwenden, um einen Zeiger zu initialisieren, der nicht `const` ist.  Standardmäßig oder wenn **\/Zc:strictStrings\-** angegeben wird, werden vom Compiler nicht die Standard\-Qualifikationen von C\+\+ `const` für Zeichenfolgenzeiger erzwungen, die mithilfe von Zeichenfolgenliteralen initialisiert werden.  
  
 Verwenden Sie die Option **\/Zc:strictStrings**, um die Kompilierung von fehlerhaftem Code zu verhindern.  Dieses Beispiel zeigt, wie ein einfacher Deklarationsfehler zu einem Absturz während der Laufzeit führt:  
  
```cpp  
// strictStrings_off.cpp  
// compile by using: cl /W4 strictStrings_off.cpp  
int main() {  
   wchar_t* str = L"hello";  
   str[2] = L'a'; // run-time error: access violation  
}  
```  
  
 Wenn **\/Zc:strictStrings** aktiviert ist, meldet der gleiche Code für einen Fehler in der Deklaration von `str`.  
  
```cpp  
// strictStrings_on.cpp  
// compile by using: cl /Zc:strictStrings /W4 strictStrings_on.cpp  
int main() {  
   wchar_t* str = L"hello"; // error: Conversion from string literal   
   // loses const qualifier  
   str[2] = L'a';   
}  
```  
  
 Wenn Sie `auto` verwenden, um einen Zeichenfolgenzeiger zu deklarieren, erstellt der Compiler die richtige `const` Zeigertypdeklaration für Sie.  Ein Versuch, den Inhalt eines `const`\-Zeigers zu ändern, wird vom Compiler als Fehler gemeldet.  
  
> [!NOTE]
>  Die C\+\+\-Standardbibliothek in [!INCLUDE[cpp_dev12_long](../../build/reference/includes/cpp_dev12_long_md.md)] unterstützt nicht die **\/Zc:strictStrings**\-Compileroption in Debugversionen.  Wenn Sie mehrere Fehler [C2665](../../error-messages/compiler-errors-2/compiler-error-c2665.md) in der Buildausgabe finden, kann dies die Ursache sein.  
  
 Weitere Informationen über Konformitätsprobleme in Visual C\+\+ finden Sie unter [Nicht dem Standard entsprechendes Verhalten](../../cpp/nonstandard-behavior.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie den Ordner **C\/C\+\+** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Befehlszeile** aus.  
  
4.  Ändern Sie die Eigenschaft **Zusätzliche Optionen**, damit sie `/Zc:strictStrings` einschließt, und wählen Sie dann **OK** aus.  
  
## Siehe auch  
 [\/Zc \(Übereinstimmung\)](../../build/reference/zc-conformance.md)