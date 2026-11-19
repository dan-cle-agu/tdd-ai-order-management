Congratulations! 🎉 At this point you’ve built and tested both the OrderTracker logic and the Flask API. Now it’s time to run the full application and see it in action.

# Starting the Server

From the project root (`starter/`), run:
```
python -m backend.app
```

- In the Workspace: open the *Links* menu and click *Flask App* to launch the application in a new browser tab.
- Locally: open http://127.0.0.1:5000 in your browser.

# Interacting with the App

When you open the app in your browser, you should see the provided frontend. With your backend complete, you can now:

- Add an order using the form.
- List all orders to confirm they’re being stored.
- Update an order’s status (e.g., from _pending_ to _shipped_).
- Filter orders by status to check your query routes.

Note: Data is stored in memory only. If you restart the Flask server, all orders will be cleared.

# (Optional) Direct API Interactions

The frontend is just a client of your API — it calls the same routes you implemented under `/api/orders/...`. If you’d like, you can also interact with the API directly.

- *Example: Add a new order (POST)*
```
curl -X POST http://127.0.0.1:5000/api/orders \
     -H "Content-Type: application/json" \
     -d '{
       "order_id": "CURL001",
       "item_name": "Headphones",
       "quantity": 1,
       "customer_id": "CUST123"
     }'
```

- *Example: Retrieve that order (GET)*
```
curl http://127.0.0.1:5000/api/orders/CURL001
```

The *frontend UI loads at* `/` (or `/index`), while your *API lives under* `/api/orders...`. Both should now work together.

# Tips and Troubleshooting

## Import errors when running tests

Always run `pytest` from the project root (`starter/`). Running it from inside `backend/` will break imports.

## Port already in use (local environment setup)

If something else is running on port 5000, open `backend/app.py` and update:
```
app.run(host="0.0.0.0", port=8000, debug=True)
```

Then visit `http://127.0.0.1:8000`.

This issue should typically not be possible in a Udacity Workspace, but if you do encounter it, try restarting the Workspace.

## Autoreload behavior

Flask runs in debug mode. Saving a file will restart the server automatically. It may look like it starts twice — this is expected.

## Reading error messages

- When running pytest, look for the traceback to see which test failed and why.
- When running the Flask server, errors will appear in the terminal where the server is running.

# Adding Your Reflection

Add a short *reflection* to `starter/README.md` (2–5 bullet points or ~80–150 words) covering:

- One design decision or trade-off you made in `OrderTracker` or the API routes.
- One testing insight (e.g., a failing test that caught a bug or drove a refactor).
- One next step you’d take if you continued the project (e.g., DELETE endpoint, persistent storage, stricter validation).
Replace this portion of `starter/README.md` with appropriate text. You can leave the file tree below.

```
# Udatracker Starter Code

This directory contains the starter code for the Udatracker project. The initial structure of directories and files is described below.
```
