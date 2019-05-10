---
title: Friend-Assemblys (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- friend assemblies, Visual C++
ms.assetid: 8d55fee0-b7c2-4fbe-a23b-dfe424dc71cd
ms.openlocfilehash: 05b9d8bcf5d7364e1dcd31940bc0db64a5e605f1
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447303"
---
# <a name="friend-assemblies-c"></a>Friend-Assemblys (C++)

Für Laufzeiten anwendbar die *Friend-Assemblys* Sprachfunktion stellt die Typen, die im Namespace-Gültigkeitsbereich oder im globalen Bereich in einer Assemblykomponente zugegriffen werden kann, um eine oder mehrere Clientassemblys oder NETMODULE-Dateien sind.

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

#### <a name="to-make-types-at-namespace-scope-or-global-scope-in-an-assembly-component-accessible-to-a-client-assembly-or-netmodule"></a>Typen im Namespace-Gültigkeitsbereich oder im globalen Gültigkeitsbereich in einer Assemblykomponente für eine Clientassembly oder eine NETMODULE-Datei zugänglich zu machen

1. Geben Sie in der Komponente, die einem Assemblyattribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, und übergeben Sie den Namen des Client-Assembly oder NETMODULE-Datei, die Typen im Namespace-Gültigkeitsbereich oder im globalen Gültigkeitsbereich in der Komponente zugegriffen wird.  Sie können mehrere Clientassemblys oder NETMODULE-Dateien angeben, indem zusätzliche Attribute angeben.

1. In der Clientassembly oder eine NETMODULE-Datei, wenn Sie die Komponentenassembly mit verweisen `#using`, übergeben die `as_friend` Attribut.  Bei Angabe der `as_friend` Attribut für eine Assembly, der nicht `InternalsVisibleToAttribute`, eine Laufzeitausnahme wird ausgelöst, wenn Sie versuchen, Zugriff auf einen Typ im Namespace-Gültigkeitsbereich oder im globalen Gültigkeitsbereich in der Komponente.

Ein Buildfehler führt, wenn die Assembly mit der <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attribut verfügt nicht über einen starken Namen, aber die Clientassembly, die verwendet die `as_friend` Attribut führt.

Obwohl Typen im Gültigkeitsbereich des Namespace und den globalen Bereich auf eine Client-Assembly oder eine NETMODULE-Datei bekannt sind können, ist Memberzugriff weiterhin wirksam.  Sie können keine z. B. einen privaten Member zugreifen.

Zugriff auf alle Typen in einer Assembly muss explizit erteilt werden.  Beispielsweise ist Assembly C keinen Zugriff auf alle Typen in Assembly A haben Assembly C verweist auf Assembly B und Assembly B hat Zugriff auf alle Typen in Assembly a

Informationen dazu, wie sich – d. h. wie Sie einen starken Namen zu geben – eine Assembly, die erstellt wird, mithilfe des Microsoft C++ -Compiler, finden Sie unter [Assemblys mit starken Namen (Assemblysignierung) (C++/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).

Als Alternative zum Verwenden des Features der Friend-Assemblys können <xref:System.Security.Permissions.StrongNameIdentityPermission> Zugriff auf einzelne Typen eingeschränkt.

### <a name="requirements"></a>Anforderungen

Compileroption: **/clr**

### <a name="examples"></a>Beispiele

Im folgenden Codebeispiel wird eine Komponente, die eine Clientassembly angibt, die Zugriff auf die Typen in der Komponente definiert.

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

Im nächste Codebeispiel greift auf einen privaten Typ in der Komponente.

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

Im nächste Codebeispiel wird eine Komponente definiert, aber keine Clientassembly, die Zugriff auf die Typen in der Komponente haben.

Beachten Sie, dass die Komponente verknüpft wurde **/ opt: Noref**. Dadurch wird sichergestellt, dass private Typen in den Metadaten der Komponente, ausgegeben werden, die nicht erforderlich wenn ist die `InternalsVisibleTo` Attribut vorhanden ist. Weitere Informationen finden Sie unter [/OPT (Optimierungen)](../build/reference/opt-optimizations.md).

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

Das folgende Codebeispiel definiert einen Client, der versucht, einen privaten Typ in einer Komponente zugreifen, die nicht auf die privaten Typen Zugriff. Aufgrund des Verhaltens der Laufzeit Wenn Sie die Ausnahme abfangen möchten müssen Sie versuchen, einen privaten Typ in eine Hilfsfunktion.

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

Im nächste Codebeispiel zeigt, wie eine Komponente von starken Namen zu erstellen, die eine Clientassembly angibt, die Zugriff auf die Typen der Komponente verfügt.

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

Beachten Sie, dass die Komponente seinen öffentlichen Schlüssel angeben muss. Es wird empfohlen, Sie führen die folgenden Befehle nacheinander an einer Eingabeaufforderung zum Erstellen eines Schlüsselpaars und Abrufen des öffentlichen Schlüssels:

**sn -d friend_assemblies.snk**

**sn -k friend_assemblies.snk**

**sn -i friend_assemblies.snk friend_assemblies.snk**

**sn -pc friend_assemblies.snk key.publickey**

**sn -tp key.publickey**

Im nächste Codebeispiel greift auf einen privaten Typ in der Komponente starkem Namen.

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

[Komponentenerweiterungen für Laufzeitplattformen](../extensions/component-extensions-for-runtime-platforms.md)
