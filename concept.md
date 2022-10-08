```ts
// Option 1
class Arrow implements Projectile {
	template = myTemplate;
	speed = 40;

	public build(part) {
		part.Mover.Enabled = true;
	}

	public cleanup(part) {
		part.Mover.Enabled = false;
	}

	public move(part, pos, dir) {
		part.Position = pos;
		part.Mover.Velocity = dir * self.speed;
	}
}

// Option 2
const projectile = new Projectile({
	template = myTemplate,
	speed = 40;

	build = (part) => {
		part.Mover.Enabled = true;
	},

	cleanup = (part) => {
		part.Mover.Enabled = false;
	},

	move = (part, pos, dir) => {
		part.Position = pos;
		part.Mover.Velocity = dir * self.speed;
	},
})

const dispenser = new Dispenser(projectile, parent, {
	rate = 5,
});

dispenser.emit(50);
```
