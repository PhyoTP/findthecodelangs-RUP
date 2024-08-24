# Find the code langs showcase
This is a website showcasing my [roblox game](https://www.roblox.com/share?code=c24371b39f9de146a3183c7205141a2d&type=ExperienceDetails&stamp=1718626359965) as a 3d model, exported to unity 
and built on [github pages](https://phyotp.github.io/findthecodelangs-RUP)
 as my submission for fraps.hackclub.com
code for camera:
```cs

using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.SceneManagement;

public class CameraScript : MonoBehaviour
{
    private GameObject model;
    void Awake()
    {
        Cursor.lockState = CursorLockMode.Locked;
        model = GameObject.Find("ftclModel");
    }

    void Update()
    {
        //mouse control
        transform.RotateAround(model.transform.position, Vector3.up, Input.GetAxis("Mouse X"));
        transform.RotateAround(model.transform.position, -transform.right, Input.GetAxis("Mouse Y"));

        if (Cursor.lockState == CursorLockMode.None && Input.GetMouseButtonDown(1))
        {
            Cursor.lockState = CursorLockMode.Locked;
        }
        else if (Cursor.lockState == CursorLockMode.Locked && Input.GetKeyDown(KeyCode.Escape))
        {
            Cursor.lockState = CursorLockMode.None;
        }

        
    }


}```
