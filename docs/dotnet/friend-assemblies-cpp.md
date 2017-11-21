---
title: Friend-Assemblys (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: friend assemblies, Visual C++
ms.assetid: 8d55fee0-b7c2-4fbe-a23b-dfe424dc71cd
caps.latest.revision: "27"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 42ccf247d88efc6e0e9378ee52a4749ddc3c2b6f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="friend-assemblies-c"></a>Friend-Assemblys (C++)
Für Laufzeiten auf anwendbar die *Friend-Assemblys* Sprachfunktion können Sie Typen, die auf Namespace-Gültigkeitsbereich oder im globalen Gültigkeitsbereich in einer Assemblykomponente Clientassemblys oder netmodule zugreifen können.  
  
## <a name="all-runtimes"></a>Alle Laufzeiten  
 **Hinweise**  
  
 (Diese Sprachfunktion wird in alle Laufzeiten nicht unterstützt.)  
  
## <a name="windows-runtime"></a>Windows-Runtime  
 **Hinweise**  
  
 (Diese Sprachfunktion wird in der Windows-Runtime nicht unterstützt.)  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
 **Hinweise**  
  
#### <a name="to-make-types-at-namespace-scope-or-global-scope-in-an-assembly-component-accessible-to-a-client-assembly-or-netmodule"></a>Typen im Namespace oder im globalen Gültigkeitsbereich in einer Assemblykomponente vornehmen können eine Client-Assembly oder netmodule zugreifen  
  
1.  Geben Sie in der Komponente ein Assemblyattribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, und übergeben Sie den Namen des Client-Assembly oder NETMODULE-Datei, die Typen im Namespace oder im globalen Gültigkeitsbereich in der Komponente zugegriffen wird.  Sie können mehrere Clientassemblys oder NETMODULE-Dateien angeben, indem Sie zusätzliche Attribute angeben.  
  
2.  In der Clientassembly oder eine NETMODULE-Datei, wenn Sie mithilfe der Komponentenassembly verweisen `#using`, übergeben die `as_friend` Attribut.  Bei Angabe der `as_friend` Attribut für eine Assembly, der nicht `InternalsVisibleToAttribute`, eine Laufzeitausnahme wird ausgelöst, wenn Sie versuchen, Zugriff auf einen Typ auf den Namespace oder im globalen Gültigkeitsbereich in der Komponente.  
  
 Ein Buildfehler führt, wenn die Assembly, die enthält die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attribut verfügt nicht über einen starken Namen, aber die Clientassembly, die verwendet die `as_friend` Attribut führt.  
  
 Obwohl die Typen im Namespace-Gültigkeitsbereich und globalen Gültigkeitsbereich zu einem Client-Assembly oder NETMODULE bekannt sein können, ist Memberzugriff weiterhin wirksam.  Sie können keine z. B. einen privaten Member zugreifen.  
  
 Zugriff auf alle Typen in einer Assembly muss explizit erteilt werden.  Beispielsweise ist Assembly C keinen Zugriff auf alle Typen in der Assembly A Wenn Assembly C verweist auf Assembly B und Assembly B Zugriff auf alle Typen in Assembly a hat  
  
 Informationen zum Signieren – d. h., wie Sie einen starken Namen zu geben – eine Assembly, die mithilfe von Visual C++-Compilers finden Sie unter [Assemblys mit starken Namen (Signieren von Assemblys) (C + c++ / CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).  
  
 Als Alternative zum Verwenden des Features der Friend-Assemblys können <xref:System.Security.Permissions.StrongNameIdentityPermission> Zugriff auf die einzelnen Typen eingeschränkt.  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
### <a name="examples"></a>Beispiele  
 Das folgende Codebeispiel definiert eine Komponente, die eine Clientassembly gibt an, die auf die Typen in der Komponente möglich ist.  
  
```cpp  
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
  
 Das nächste Codebeispiel greift auf einen privaten Typ in der Komponente.  
  
```cpp  
// friend_assemblies_2.cpp  
// compile by using: /clr  
#using "friend_assemblies.dll" as_friend  
  
int main() {  
   Class1 ^ a = gcnew Class1;  
   a->Test_Public();  
}  
```  
  
```Output  
Class1::Test_Public  
```  
  
 Im nächste Codebeispiel wird eine Komponente definiert jedoch keine Clientassembly, die Zugriff auf die Typen in der Komponente haben.  
  
 Beachten Sie, dass die Komponente mit verknüpft ist **/ opt: Noref**. Dadurch wird sichergestellt, dass private Typen in den Metadaten der Komponente, ausgegeben werden, nicht ist erforderlich, wenn die `InternalsVisibleTo` -Attribut vorhanden ist. Weitere Informationen finden Sie unter [/OPT (Optimierungen)](../build/reference/opt-optimizations.md).  
  
```cpp  
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
  
 Das folgende Codebeispiel definiert einen Client, der versucht, einen privaten Typ in einer Komponente auf, die nicht auf die privaten Typen Zugriff. Aufgrund der Verhalten der Laufzeit Wenn Sie die Ausnahme abfangen möchten müssen Sie versuchen, einen privaten Typ in eine Hilfsfunktion zugreifen.  
  
```cpp  
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
  
```Output  
caught an exception  
```
  
 Das nächste Codebeispiel zeigt, wie zum Erstellen einer starken Namen-Komponente, die eine Clientassembly gibt an, die Zugriff auf die Typen in der Komponente haben.  
  
```cpp  
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
  
 Beachten Sie, dass die Komponente seinen öffentlichen Schlüssel angeben muss. Es wird empfohlen, Sie werden die folgenden Befehle nacheinander ausgeführt, an der Eingabeaufforderung zum Erstellen eines Schlüsselpaars und den öffentlichen Schlüssel abrufen:  
  
 **"sn" -d friend_assemblies.snk**  
  
 **sn – k friend_assemblies.snk**  
  
 **"sn" -i friend_assemblies.snk friend_assemblies.snk**  
  
 **"sn" -pc friend_assemblies.snk key.publickey**  
  
 **"sn" - Tp key.publickey**  
  
 Das nächste Codebeispiel greift auf einen privaten Typ in der Komponente starken Namen zu.  
  
```cpp  
// friend_assemblies_6.cpp  
// compile by using: /clr /link /keyfile:friend_assemblies.snk  
#using "friend_assemblies_5.dll" as_friend  
  
int main() {  
   Class1 ^ a = gcnew Class1;  
   a->Test_Public();  
}  
```  
  
```Output  
Class1::Test_Public  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)