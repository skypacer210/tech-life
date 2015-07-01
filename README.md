# tech-life
技术人生

```
struct apr_queue_t {
    void              **data;
    unsigned int        nelts; 			/**< # elements */
    unsigned int        in;    			/**< next empty location */
    unsigned int        out;   			/**< next filled location */
    unsigned int        bounds;			/**< max size of queue */
    unsigned int        full_waiters;
    unsigned int        empty_waiters;
    apr_thread_mutex_t *one_big_mutex;	/**< 典型的用一个mutex */
    apr_thread_cond_t  *not_empty;		/**< 加一个非空条件变量 */
    apr_thread_cond_t  *not_full;		/**< 加一个非满条件变量 */
    int                 terminated;
};

```