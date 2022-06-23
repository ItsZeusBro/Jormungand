# Jormungand
## A Python Plugin/Plugout that Generates Python in your Source Files from your Hydra Schema
![download](https://user-images.githubusercontent.com/107733608/175232586-7ad0664a-a3c3-4495-b1bf-dcb61fe54cc2.jpg)

    {
      plugout:{
            //create a special purpose plugout here using Hydra's api to do some plugin development on the fly
            //and see how it interacts with the rest of your hydra files. Hydra's full api is directly exposed
            //to every hydra file by default, because the interpreter is what recognizes those calls.
            pythonv3:{
                //create your python based plugout for Hydra output evaluation (hydra's evalated JSON gets injested by 
                //your Python as the keyword "output")
                //this code block creates a python 3 file and imports the Hydra JSON output (called output) 
                //every chance Hydra gets for immediate feedback.
                //So do something with output.whatever in python
            }
      }
      Hydra:{
            objName3:{
              type: "Class",
              props:{
                size: "18",
                desc: "weighty thing"
              },
              methods:{
                get_weight: {
                    plugin: "Jormungand"
                    code:{
                        //this feature gets ignored if you do not insert the associated language plugin
                        //insert python code here that would go inside of func get_weight: in your python file
                        return self.size
                    }

                }

            }
       }
    }
