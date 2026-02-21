# Sarcric28
Cricket game
using UnityEngine;

public class CricketBall : MonoBehaviour
{
    public float speed = 50f;
    public float spin = 0.5f;
    private Rigidbody rb;

    void Start()
    {
        rb = GetComponent<Rigidbody>();
        // Launch the ball
        rb.velocity = transform.forward * speed;
    }

    void FixedUpdate()
    {
        // Add spin effect (curves the ball)
        rb.velocity += transform.right * spin;
        
        // Gravity is automatic with Rigidbody
    }

    void OnTriggerEnter(Collider other)
    {
        // Detect if ball hits bat, fielder, or boundary
        if (other.tag == "Bat")
        {
            Debug.Log("Ball hit! Running...");
        }
    }
}
