---
title: "Friend-Assemblys (C++)"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Friend-Assemblys, Visual C++"
ms.assetid: 8d55fee0-b7c2-4fbe-a23b-dfe424dc71cd
caps.latest.revision: 27
caps.handback.revision: "27"
ms.author: "mblome"
manager: "ghogen"
---
# Friend-Assemblys (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei entsprechenden Laufzeiten macht die *Friend\-Assembly\-Sprachfunktion*\-Typen, die im Gültigkeitsbereich des Namespaces gefunden oder im globalen Bereich in einer Assemblykomponente sind, die mit mindestens erforderlichen Clientassemblys oder zu .netmodules zugänglich ist.  
  
## Alle Laufzeiten  
 **Hinweise**  
  
 \(Diese Sprachfunktion ist nicht in allen Laufzeiten. unterstützt\)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Hinweise**  
  
 \(Diese Sprachfunktion wird in [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] nicht unterstützt.\)  
  
### Voraussetzungen  
 Compileroption: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Hinweise**  
  
#### Um Typen am Namespacebereich oder im globalen Bereich in einer Assemblykomponente zugänglich machen zu einer Clientassembly oder \-.netmodule  
  
1.  In der Komponente geben Sie einem Assemblyattribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, und übergeben Sie den Namen der \-.netmodules Clientassemblys oder, der Zugriffstypen am Namespacebereich oder im globalen Bereich in der Komponente ist.  Sie können mehreren Clientassemblys oder .netmodules angeben, indem Sie zusätzliche Attribute angeben.  
  
2.  In der Clientassembly oder wenn Sie die \-.netmodule Komponentenassembly verweisen, indem Sie `#using` verwenden, übergeben Sie das `as_friend`\-Attribut.  Wenn Sie das Attribut `as_friend` für eine Assembly angeben, die nicht `InternalsVisibleToAttribute` angibt, wird eine Laufzeitausnahme ausgelöst, wenn Sie versuchen, auf einen Typ im Gültigkeitsbereich des Namespaces gefunden oder im globalen Bereich in der Komponente zugreifen.  
  
 Ein Buildfehler tritt auf, wenn die Assembly, die das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> enthält keinen starken Namen, aber den Client hat, die, Assembly, die das `as_friend`\-Attribut verwendet, führt.  
  
 Obwohl Typen am Namespacebereich und im globalen Bereich zu einer Clientassembly oder \-.netmodule werden können, ist Memberbarrierefreiheit noch wirksam.  Beispielsweise können Sie ein privates Member zugreifen.  
  
 Sämtlicher Zugriff auf Typen in einer Assembly muss explizit gewährt werden.  Beispielsweise, die Typen in Assembly C keinen Zugriff für alle verfügt, Assembly A ein, wenn C\-Referenz\-Assembly Assembly B und Assembly B Zugriff für alle verfügt, Assembly A.  
  
 Informationen darüber, wie der Zugriffsart von Typen aus einer Assembly, finden Sie unter [Typsichtbarkeit](../misc/type-visibility.md).  
  
 Informationen darüber, wie zu, SIGN\-dass ist, wie einen starken Namen \- Ein zur Assembly, die erstellt wurde, indem Sie den Visual C\+\+\-Compiler verwendet, finden Sie unter [Assemblys mit starken Namen \(Assemblysignierung\)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).  
  
 Wie eine Alternative zur Verwendung der Funktion Friend\-Assemblys, Sie <xref:System.Security.Permissions.StrongNameIdentityPermission> verwenden kann, um Zugriff auf einzelne Typen einzuschränken.  
  
### Voraussetzungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 Im folgenden Codebeispiel wird eine Komponente, die eine Clientassembly angibt, die Zugriff auf die Typen in der Komponente verfügt.  
  
```  
// friend_assemblies.cpp  
// compile by using: /clr /LD  
using namespace System::Runtime::CompilerServices;  
using namespace System;  
// an assembly attribute, not bound to a type  
[assembly:InternalsVisibleTo("friend_assemblies_2")];  
  
ref class Class1 {  
public:  
   void Test_Public() {  
      Console::WriteLine("Class1::Test_Public");  
   }  
};  
```  
  
 Das folgende Beispiel greift auf ein privates in die Komponente an.  
  
```  
// friend_assemblies_2.cpp  
// compile by using: /clr  
#using "friend_assemblies.dll" as_friend  
  
int main() {  
   Class1 ^ a = gcnew Class1;  
   a->Test_Public();  
}  
```  
  
 **Ausgabe**  
  
 `Class1::Test_Public`  
  
 Im folgenden Codebeispiel wird eine Komponente, aber gibt keine Clientassembly an, die Zugriff auf die Typen in der Komponente verfügt.  
  
 Beachten Sie, dass die Komponente verknüpft ist, indem Sie **\/opt:noref** verwenden.  Dadurch wird sichergestellt, dass private Typen in den Metadaten der Komponente ausgegeben werden, die nicht erforderlich ist, wenn das `InternalsVisibleTo`\-Attribut vorhanden ist.  Weitere Informationen finden Sie unter [\/OPT \(Optimierungen\)](../build/reference/opt-optimizations.md).  
  
```  
// friend_assemblies_3.cpp  
// compile by using: /clr /LD /link /opt:noref  
using namespace System;  
  
ref class Class1 {  
public:  
   void Test_Public() {  
      Console::WriteLine("Class1::Test_Public");  
   }  
};  
```  
  
 Im folgenden Codebeispiel wird ein Client definiert, dem die versucht, auf ein privates zuzugreifen in eine Komponente, die nicht auf den privaten Typen gibt.  Aufgrund des Verhaltens der Laufzeit, wenn die Ausnahme abfangen möchten, müssen Sie versuchen, auf ein privates zuzugreifen in einer Hilfsfunktion.  
  
```  
// friend_assemblies_4.cpp  
// compile by using: /clr  
#using "friend_assemblies_3.dll" as_friend  
using namespace System;  
  
void Test() {  
   Class1 ^ a = gcnew Class1;  
}  
  
int main() {  
   // to catch this kind of exception, use a helper function  
   try {  
      Test();     
   }  
   catch(MethodAccessException ^ e) {  
      Console::WriteLine("caught an exception");  
   }  
}  
```  
  
 **Ausgabe**  
  
 `caught an exception`  
  
 Das folgende Codebeispiel zeigt, wie eine Komponente mit starkem Namen erstellt, die eine Clientassembly angibt, die Zugriff auf die Typen in der Komponente verfügt.  
  
```  
// friend_assemblies_5.cpp  
// compile by using: /clr /LD /link /keyfile:friend_assemblies.snk  
using namespace System::Runtime::CompilerServices;  
using namespace System;  
// an assembly attribute, not bound to a type  
  
[assembly:InternalsVisibleTo("friend_assemblies_6, PublicKey=00240000048000009400000006020000002400005253413100040000010001000bf45d77fd991f3bff0ef51af48a12d35699e04616f27ba561195a69ebd3449c345389dc9603d65be8cd1987bc7ea48bdda35ac7d57d3d82c666b7fc1a5b79836d139ef0ac8c4e715434211660f481612771a9f7059b9b742c3d8af00e01716ed4b872e6f1be0e94863eb5745224f0deaba5b137624d7049b6f2d87fba639fc5")];  
  
private ref class Class1 {  
public:  
   void Test_Public() {  
      Console::WriteLine("Class1::Test_Public");  
   }  
};  
```  
  
 Beachten Sie, dass die Komponente deren öffentlichen Schlüssel angeben muss.  Es wird empfohlen, dass Sie die folgenden Befehle sequenziell an einer Eingabeaufforderung ausführen, ein Schlüsselpaar zu erstellen und den öffentlichen Schlüssel abrufen:  
  
 **sn \-d friend\_assemblies.snk**  
  
 **sn \-k friend\_assemblies.snk**  
  
 **sn \-i friend\_assemblies.snk friend\_assemblies.snk**  
  
 **sn \-pc friend\_assemblies.snk key.publickey**  
  
 **sn \-tp key.publickey**  
  
 Das folgende Beispiel greift auf ein privates in die Komponente mit starkem Namen zu.  
  
```  
// friend_assemblies_6.cpp  
// compile by using: /clr /link /keyfile:friend_assemblies.snk  
#using "friend_assemblies_5.dll" as_friend  
  
int main() {  
   Class1 ^ a = gcnew Class1;  
   a->Test_Public();  
}  
```  
  
 **Ausgabe**  
  
 `Class1::Test_Public`  
  
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)