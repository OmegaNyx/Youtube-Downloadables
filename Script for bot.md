 begin
     Function.Execute("AntiAuto")
     
     Keyboard.Hold keys("{<tab>}")
     Keyboard.Release keys("{<tab>}")
     Function.Execute("Heal")
     Function.Execute("Loot")
     // RGB of the digi you want to attack
     if  Color.At coordinate is (RGB)("130", "182", "214", "608", "64")
          begin loop()
               Keyboard.Hold keys("1")
               Keyboard.Release keys("1")
               Keyboard.Hold keys("{<f2>}")
               Keyboard.Release keys("{<f2>}")
               Keyboard.Hold keys("{<f1>}")
               Keyboard.Release keys("{<f1>}")
               Function.Execute("Loot")
               Function.Execute("Heal")
               Function.Execute("AntiAuto")
               
               // Same co ordinates of the previous check
               if  Color.At coordinate is not (RGB)("130", "182", "214", "608", "64")
                    begin
                         Macro.Restart("no")
                    end
          end
     // RGB of the red square of aggro monsters around the fist
     if  Color.At coordinate is (RGB)("164", "0", "29", "409", "69")
          begin loop()
               Keyboard.Hold keys("1")
               Keyboard.Release keys("1")
               Keyboard.Hold keys("{<f2>}")
               Keyboard.Release keys("{<f2>}")
               Keyboard.Hold keys("{<f1>}")
               Keyboard.Release keys("{<f1>}")
               Function.Execute("Heal")
               Function.Execute("TAB")
               Function.Execute("AntiAuto")
              
               // Same RGB from above
               if  Color.At coordinate is not (RGB)("164", "0", "29", "409", "69")
                    begin
                         Macro.Restart("no")
                    end
          end
     // Same RGB from above
     if  Color.At coordinate is not (RGB)("164", "0", "29", "409", "69")
          begin
               Macro.Restart("no")
          end
 end

function("Heal")
     // RGB of a part of digimon hp , preferable about 25% of your digimon HP , this uses Hp DISK in slot F7
     if  Color.At coordinate is not (RGB)("132", "29", "18", "131", "124")
          begin
               Keyboard.Hold keys("{<f7>}")
               Keyboard.Release keys("{<f7>}")
          end
     // RGB of a part of digimon hp to use FOOD in slot 7 , preferably specify about 50% of digimon HP
     if  Color.At coordinate is not (RGB)("132", "29", "18", "168", "124")
          begin
               Keyboard.Hold keys("7")
               Keyboard.Release keys("7")
          end
     // RGB for Digimon DS to use DS DISK in slot F8
     if  Color.At coordinate is not (RGB)("0", "138", "150", "127", "138")
          begin
               Keyboard.Hold keys("{<f8>}")
               Keyboard.Release keys("{<f8>}")
          end
     // RGB for TAMER DS , slot 8
     if  Color.At coordinate is not (RGB)("0", "206", "220", "138", "66")
          begin
               Keyboard.Hold keys("8")
               Keyboard.Release keys("8")
          end
function

function("Loot")
     begin
          Keyboard.Hold keys("4")
          Keyboard.Release keys("4")
     end
function

function("TAB")
     // If target doesnt have HP, tab to next one.
     if  Color.At coordinate is not (RGB)("133", "26", "19", "401", "55")
          and
          Color.At coordinate is not (RGB)("165", "43", "34", "401", "55")
          begin
               Keyboard.Hold keys("{<tab>}")
               Keyboard.Release keys("{<tab>}")
               Function.Execute("Heal")
          end
function

function("AntiAuto")
     begin
          if  Color.Pixel pattern can be located on screen("13,77,186,0,110,9,61,169,0,180,18,95,192,200,-290,2,59,169,0,110,10,63,171,0,180,11,72,177", "0")
               begin
                    Color.Wait for and locate pixel pattern("13,77,186,0,110,9,61,169,0,180,18,95,192,200,-290,2,59,169,0,110,10,63,171,0,180,11,72,177", "10", "x", "y")
                    Variable.Evaluate (Math)("{y}+45", "y1")
                    Variable.Evaluate (Math)("{y}+55", "y2")
                    Variable.Evaluate (Math)("{y}+65", "y3")
                    Variable.Evaluate (Math)("{x}+10", "x4")
                    Variable.Evaluate (Math)("{x}-10", "x5")
                    Variable.Evaluate (Math)("{x}-13", "xIcon1")
                    Variable.Evaluate (Math)("{x}+37", "xIcon2")
                    Variable.Evaluate (Math)("{x}+87", "xIcon3")
                    Variable.Evaluate (Math)("{x}+137", "xIcon4")
                    Variable.Evaluate (Math)("{x}+187", "xIcon5")
                    Variable.Evaluate (Math)("{y}+145", "yTopRow")
                    Variable.Evaluate (Math)("{y}+195", "yBottomRow")
                    Color.Get color at coordinate (RGB)("{x}", "{y1}", "r1", "g1", "b1")
                    Color.Get color at coordinate (RGB)("{x}", "{y2}", "r2", "g2", "b2")
                    Color.Get color at coordinate (RGB)("{x}", "{y3}", "r3", "g3", "b3")
                    Color.Get color at coordinate (RGB)("{x4}", "{y2}", "r4", "g4", "b4")
                    Color.Get color at coordinate (RGB)("{x5}", "{y2}", "r5", "g5", "b5")
                    Macro.Pause("50")
                    if  Color.Near coordinate is within (RGB range)("{r1}", "{g1}", "{b1}", "5", "{xIcon1}", "{yTopRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r2}", "{g2}", "{b2}", "5", "{xIcon1}", "{yTopRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r3}", "{g3}", "{b3}", "5", "{xIcon1}", "{yTopRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r4}", "{g4}", "{b4}", "5", "{xIcon1}", "{yTopRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r5}", "{g5}", "{b5}", "5", "{xIcon1}", "{yTopRow}", "11")
                         begin
                              Mouse.Click at coordinate("{xIcon1}", "{yTopRow}", "Left")
                         end
                    Macro.Pause("50")
                    if  Color.Near coordinate is within (RGB range)("{r1}", "{g1}", "{b1}", "5", "{xIcon2}", "{yTopRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r2}", "{g2}", "{b2}", "5", "{xIcon2}", "{yTopRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r3}", "{g3}", "{b3}", "5", "{xIcon2}", "{yTopRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r4}", "{g4}", "{b4}", "5", "{xIcon2}", "{yTopRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r5}", "{g5}", "{b5}", "5", "{xIcon2}", "{yTopRow}", "11")
                         begin
                              Mouse.Click at coordinate("{xIcon2}", "{yTopRow}", "Left")
                         end
                    Macro.Pause("50")
                    if  Color.Near coordinate is within (RGB range)("{r1}", "{g1}", "{b1}", "5", "{xIcon3}", "{yTopRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r2}", "{g2}", "{b2}", "5", "{xIcon3}", "{yTopRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r3}", "{g3}", "{b3}", "5", "{xIcon3}", "{yTopRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r4}", "{g4}", "{b4}", "5", "{xIcon3}", "{yTopRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r5}", "{g5}", "{b5}", "5", "{xIcon3}", "{yTopRow}", "11")
                         begin
                              Mouse.Click at coordinate("{xIcon3}", "{yTopRow}", "Left")
                         end
                    Macro.Pause("50")
                    if  Color.Near coordinate is within (RGB range)("{r1}", "{g1}", "{b1}", "5", "{xIcon4}", "{yTopRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r2}", "{g2}", "{b2}", "5", "{xIcon4}", "{yTopRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r3}", "{g3}", "{b3}", "5", "{xIcon4}", "{yTopRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r4}", "{g4}", "{b4}", "5", "{xIcon4}", "{yTopRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r5}", "{g5}", "{b5}", "5", "{xIcon4}", "{yTopRow}", "11")
                         begin
                              Mouse.Click at coordinate("{xIcon4}", "{yTopRow}", "Left")
                         end
                    Macro.Pause("50")
                    if  Color.Near coordinate is within (RGB range)("{r1}", "{g1}", "{b1}", "5", "{xIcon5}", "{yTopRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r2}", "{g2}", "{b2}", "5", "{xIcon5}", "{yTopRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r3}", "{g3}", "{b3}", "5", "{xIcon5}", "{yTopRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r4}", "{g4}", "{b4}", "5", "{xIcon5}", "{yTopRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r5}", "{g5}", "{b5}", "5", "{xIcon5}", "{yTopRow}", "11")
                         begin
                              Mouse.Click at coordinate("{xIcon5}", "{yTopRow}", "Left")
                         end
                    Macro.Pause("50")
                    if  Color.Near coordinate is within (RGB range)("{r1}", "{g1}", "{b1}", "5", "{xIcon1}", "{yBottomRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r2}", "{g2}", "{b2}", "5", "{xIcon1}", "{yBottomRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r3}", "{g3}", "{b3}", "5", "{xIcon1}", "{yBottomRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r4}", "{g4}", "{b4}", "5", "{xIcon1}", "{yBottomRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r5}", "{g5}", "{b5}", "5", "{xIcon1}", "{yBottomRow}", "11")
                         begin
                              Mouse.Click at coordinate("{xIcon1}", "{yBottomRow}", "Left")
                         end
                    Macro.Pause("50")
                    if  Color.Near coordinate is within (RGB range)("{r1}", "{g1}", "{b1}", "5", "{xIcon2}", "{yBottomRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r2}", "{g2}", "{b2}", "5", "{xIcon2}", "{yBottomRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r3}", "{g3}", "{b3}", "5", "{xIcon2}", "{yBottomRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r4}", "{g4}", "{b4}", "5", "{xIcon2}", "{yBottomRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r5}", "{g5}", "{b5}", "5", "{xIcon2}", "{yBottomRow}", "11")
                         begin
                              Mouse.Click at coordinate("{xIcon2}", "{yBottomRow}", "Left")
                         end
                    Macro.Pause("50")
                    if  Color.Near coordinate is within (RGB range)("{r1}", "{g1}", "{b1}", "5", "{xIcon3}", "{yBottomRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r2}", "{g2}", "{b2}", "5", "{xIcon3}", "{yBottomRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r3}", "{g3}", "{b3}", "5", "{xIcon3}", "{yBottomRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r4}", "{g4}", "{b4}", "5", "{xIcon3}", "{yBottomRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r5}", "{g5}", "{b5}", "5", "{xIcon3}", "{yBottomRow}", "11")
                         begin
                              Mouse.Click at coordinate("{xIcon3}", "{yBottomRow}", "Left")
                         end
                    Macro.Pause("50")
                    if  Color.Near coordinate is within (RGB range)("{r1}", "{g1}", "{b1}", "5", "{xIcon4}", "{yBottomRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r2}", "{g2}", "{b2}", "5", "{xIcon4}", "{yBottomRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r3}", "{g3}", "{b3}", "5", "{xIcon4}", "{yBottomRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r4}", "{g4}", "{b4}", "5", "{xIcon4}", "{yBottomRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r5}", "{g5}", "{b5}", "5", "{xIcon4}", "{yBottomRow}", "11")
                         begin
                              Mouse.Click at coordinate("{xIcon4}", "{yBottomRow}", "Left")
                         end
                    Macro.Pause("50")
                    if  Color.Near coordinate is within (RGB range)("{r1}", "{g1}", "{b1}", "5", "{xIcon5}", "{yBottomRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r2}", "{g2}", "{b2}", "5", "{xIcon5}", "{yBottomRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r3}", "{g3}", "{b3}", "5", "{xIcon5}", "{yBottomRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r4}", "{g4}", "{b4}", "5", "{xIcon5}", "{yBottomRow}", "11")
                         and
                         Color.Near coordinate is within (RGB range)("{r5}", "{g5}", "{b5}", "5", "{xIcon5}", "{yBottomRow}", "11")
                         begin
                              Mouse.Click at coordinate("{xIcon5}", "{yBottomRow}", "Left")
                         end
                    Macro.Pause("50")
               end
     end
function
