---
title: "Compilerwarnung (Stufe 4) C4435"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
dev_langs: 
  - "C++"
ms.assetid: a04524af-2b71-4ff9-9729-d9d1d1904ed7
caps.latest.revision: 2
caps.handback.revision: "2"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4435
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Klasse1": Objektlayout unter \/vd2 wird aufgrund der virtuellen Basisklasse "Klasse2"  
  
 Diese Warnung ist standardmäßig deaktiviert.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 unter dem Standard kompilieren Sie Option von \/vd1, die abgeleitete Klasse verfügt über kein Feld `vtordisp` für die angegebene virtuelle Basisklasse.  Wenn \/vd2 oder `#pragma vtordisp(2)` wirksam ist, ist ein `vtordisp` Feld das vorhanden und ändert das Objektlayout.  Dies kann zu Problemen binärer Kompatibilität führen, wenn Module durch, werden kompiliert mit verschiedenen `vtordisp` Einstellungen.  
  
## Beispiel  
 Im folgenden Beispiel wird C4435 generiert.  
  
```cpp  
// C4435.cpp  
// compile with: /c /W4  
#pragma warning(default : 4435)  
class A  
{  
public:  
    virtual ~A() {}  
};  
  
class B : public virtual A  // C4435  
{};  
```  
  
## Siehe auch  
 [vtordisp](../../preprocessor/vtordisp.md)   
 [\/vd \(Konstruktionsverschiebungen deaktivieren\)](../../build/reference/vd-disable-construction-displacements.md)