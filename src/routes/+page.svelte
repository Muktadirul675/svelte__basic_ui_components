<script lang="ts">
    import BeatLoader from "$lib/comps/BeatLoader.svelte";
    import Button from "$lib/comps/Button.svelte";
    import Colors from "$lib/comps/Colors.svelte";
    import Dot from "$lib/comps/Dot.svelte";
    import Spinner from "$lib/comps/Spinner.svelte";
    import Card from "$lib/comps/card/Card.svelte";
    import CardBody from "$lib/comps/card/CardBody.svelte";
    import CardSubTitle from "$lib/comps/card/CardSubTitle.svelte";
    import CardTitle from "$lib/comps/card/CardTitle.svelte";
    import CardImage from "$lib/comps/card/CardImage.svelte";
    import CardTopImage from "$lib/comps/card/CardTopImage.svelte";
    import CardFooter from "$lib/comps/card/CardFooter.svelte";
    import Avatar from "$lib/comps/Avatar.svelte";
    import CardHeader from "$lib/comps/card/CardHeader.svelte";
    import CardText from "$lib/comps/card/CardText.svelte";
    import Divider from "$lib/comps/Divider.svelte";
    import Badge from "$lib/comps/Badge.svelte";
    import Select from "$lib/comps/Select.svelte";
</script>

<Colors />

<Select/>

<div class="w-full lg:w-2/6">
    <Card borderless={true}>
        <CardHeader>
            <div class="flex">
                <Avatar
                    size="xs"
                    name='unga bunga'
                    src="https://res.cloudinary.com/dsfybjdih/image/upload/v1714366663/JS_T_BD_20240429_105708_0000_syywtz.png"/>
                <div class="ms-3">
                    <h3 class="font-bold">Mahi Islam</h3>
                    <h3 class="text-gray">
                        Creator of nano ui
                        <span class="mx-2">
                            <Badge>Admin</Badge>
                            <Badge color='orange'>Admin</Badge>
                            <Badge variant='outline'>Admin</Badge>
                        </span>
                    </h3>
                </div>
            </div>
        </CardHeader>
        <CardBody>
            <CardText>
                Cupidatat amet proident ullamco et non dolore velit. Lorem amet nisi exercitation officia do minim adipisicing in irure aliqua qui cillum irure adipisicing. Officia duis deserunt ea esse. Minim est ut ex occaecat pariatur laborum excepteur officia est do labore ad sunt sint. Consequat non ad excepteur pariatur reprehenderit commodo cupidatat dolore sint anim.
            </CardText>
        </CardBody>
        <CardImage
            src="https://res.cloudinary.com/dsfybjdih/image/upload/v1714366663/JS_Time_BD_20240429_105708_0000_syywtz.png"
        />
        <CardFooter>
            <div class="flex">
                <div class="mx-auto">
                    Share
                </div>
                <div class="mx-auto">
                    Share
                </div>
                <div class="mx-auto">
                    Share
                </div>
            </div>
        </CardFooter>
    </Card>
    <Divider/>
</div>
