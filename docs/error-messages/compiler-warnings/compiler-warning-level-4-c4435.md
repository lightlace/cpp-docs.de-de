---
title: Compilerwarnung (Stufe 4) C4435 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: a04524af-2b71-4ff9-9729-d9d1d1904ed7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 72c29bd6d9ffdb4eabb036c61d85a6572cef8fe2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4435"></a>Compilerwarnung (Stufe 4) C4435
'class1' : Das Objektlayout unter „/vd2“ wird aufgrund der virtuellen Basis 'class2' geändert.  
  
 Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
 Kompilieren Sie unter der Standard-Option von/vd1, die abgeleitete Klasse verfügt nicht über eine `vtordisp` Feld für die angegebene virtuelle Basis.  Wenn/vd2 oder `#pragma vtordisp(2)` gültig ist, wird ein `vtordisp` Feld vorhanden ist, ändern am Objektlayout sein wird.  Dies kann zu Binärkompatibilität Problemen führen, wenn interagierenden Module mit unterschiedlichen kompiliert werden `vtordisp` Einstellungen.  
  
## <a name="example"></a>Beispiel  
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
  
## <a name="see-also"></a>Siehe auch  
 [vtordisp](../../preprocessor/vtordisp.md)   
 [/vd (Konstruktionsverschiebungen deaktivieren)](../../build/reference/vd-disable-construction-displacements.md)