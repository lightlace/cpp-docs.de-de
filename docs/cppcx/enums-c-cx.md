---
title: "Enumerationen (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 99fbbe28-c1cd-43af-9ead-60f90eba6e68
caps.latest.revision: 14
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 14
---
# Enumerationen (C++/CX)
[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] unterstützt das Schlüsselwort `public enum class`, das einem standardmäßigen C\+\+\-`scoped  enum` entspricht. Wenn Sie einen Enumerator verwenden, der durch das Schlüsselwort `public enum class` deklariert ist, müssen Sie den Enumerationsbezeichner dazu benutzen, den Umfang jedes Enumeratorwerts festzulegen.  
  
## Hinweise  
 Eine `public enum class`, die keinen Zugriffsspezifizierer hat, z. B. `public`, wird als standardmäßige [Enumeration mit C\+\+\-Bereichseinschränkung](~/cpp/enumerations-cpp.md) behandelt.  
  
 Eine `public enum class` oder `public enum struct`\-Deklaration kann einen zugrunde liegenden Typ jedes beliebigen ganzzahligen Typs haben, aber die [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] selbst erfordert, dass der Typ für eine Flags\-Enumeration ein int32\- oder uint32\-Wert ist. Die folgende Syntax beschreibt die Teile einer `public enum class` oder `public enum struct`. Weitere Informationen finden Sie unter [enum class](~/windows/enum-class-cpp-component-extensions.md).  
  
 Dieses Beispiel zeigt, wie eine öffentliche Enumerationsklasse definiert wird:  
  
 [!code-cpp[cx_enums#01](../snippets/cpp/VS_Snippets_Misc/cx_enums/cpp/class1.h#01)]  
  
 In diesem folgenden Beispiel wird zeigt, wie sie verwendet wird:  
  
 [!code-cpp[cx_enums#02](../snippets/cpp/VS_Snippets_Misc/cx_enums/cpp/class1.h#02)]  
  
## Beispiele  
 In den folgenden Beispielen wird veranschaulicht, wie eine Enumeration deklariert wird.  
  
 [!code-cpp[cx_enums#03](../snippets/cpp/VS_Snippets_Misc/cx_enums/cpp/class1.h#03)]  
  
 Im nächsten Beispiel wird gezeigt, wie Sie eine Enumeration in numerische Werte umwandeln und Vergleiche durchführen. Beachten Sie, dass die Verwendung des Enumerators `One` vom Enumerationsbezeichner `Enum1` beschränkt wird, und der Enumerator `First` wird durch `Enum2` beschränkt.  
  
 [!code-cpp[cx_enums#04](../snippets/cpp/VS_Snippets_Misc/cx_enums/cpp/class1.h#04)]  
  
## Siehe auch  
 [Typsystem](../cppcx/type-system-c-cx.md)   
 [Sprachreferenz zu Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)