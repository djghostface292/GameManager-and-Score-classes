# GameManager-and-Score-classes

# GameManager

using UnityEngine;
using UnityEngine.SceneManagement;
public class GameManager : MonoBehaviour {

    bool gameHasEnded = false;
    public float restartDelay = 1.5f;

    public void EndGame()
    {

        if (gameHasEnded == false)
        {
            gameHasEnded = true;
            Debug.Log("GAME OVER");
            Invoke("Restart", restartDelay); 
        }
    }

    void Restart()
    {
        SceneManager.LoadScene("Level1");

    }


}

# Score

using UnityEngine;
using UnityEngine.UI;

public class Score : MonoBehaviour {

    public Transform Player;
    public Text scoreText;
	
	// Update is called once per frame
	void Update () {

        scoreText.text = Player.position.z.ToString("0");
		
	}
}
