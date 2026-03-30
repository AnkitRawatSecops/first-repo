# first-repo
I'm the best 
# Medical shop
<!DOCTYPE html>
<html>
<head>
    <title>Medical Inventory</title>
</head>
<body>
    <h1>Medical Shop Dashboard</h1>
    <a href="/add">Add Medicine</a>

    <table border="1">
        <tr>
            <th>Name</th>
            <th>Quantity</th>
            <th>Price</th>
            <th>Actions</th>
        </tr>

        {% for med in medicines %}
        <tr>
            <td>{{ med[1] }}</td>
            <td>
                <form action="/update/{{ med[0] }}" method="post">
                    <input type="number" name="quantity" value="{{ med[2] }}">
                    <button type="submit">Update</button>
                </form>
            </td>
            <td>{{ med[3] }}</td>
            <td>
                <a href="/delete/{{ med[0] }}">Delete</a>
            </td>
        </tr>
        {% endfor %}
    </table>
</body>
</html>